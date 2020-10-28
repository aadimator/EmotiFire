<script>
  import { scaleLinear } from "d3-scale";

  export let probs;

  const points = [];
  const emoticons = {
    neutral: "😐",
    happy: "😀",
    angry: "😠",
    "positively surprised": "🤩",
    sad: "😥",
    "negatively surprised": "🙀",
  };

  for (const [key, value] of Object.entries(probs)) {
    points.push({ label: emoticons[key], prob: value * 100 });
  }

  console.log(points);

  const xTicks = Object.keys(probs);
  console.log(xTicks);
  const yTicks = [0, 25, 50, 75, 100];
  const padding = { top: 20, right: 15, bottom: 20, left: 25 };

  let width = 600;
  let height = 300;

  $: xScale = scaleLinear()
    .domain([0, xTicks.length])
    .range([padding.left, width - padding.right]);

  $: yScale = scaleLinear()
    .domain([0, Math.max.apply(null, yTicks)])
    .range([height - padding.bottom, padding.top]);

  $: innerWidth = width - (padding.left + padding.right);
  $: barWidth = innerWidth / xTicks.length;
</script>

<style>
  h2 {
    text-align: center;
  }

  .chart {
    width: 100%;
    max-width: 600px;
    margin: 0 auto;
  }

  svg {
    position: relative;
    width: 100%;
    height: 300px;
  }

  .tick {
    font-family: Helvetica, Arial;
    font-size: 0.725em;
    font-weight: 200;
  }

  .tick line {
    stroke: #e2e2e2;
    stroke-dasharray: 2;
  }

  .tick text {
    fill: #ccc;
    text-anchor: start;
  }

  .tick.tick-0 line {
    stroke-dasharray: 0;
  }

  .x-axis .tick text {
    text-anchor: middle;
    font-size: 1.5rem;
  }

  .bars rect {
    fill: #a11;
    stroke: none;
    opacity: 0.65;
  }
</style>

<div class="my-4">
  <h2 class="text-center text-gray-500 text-lg">Confidence</h2>

  <div
    class="chart"
    bind:clientWidth={width}
    bind:clientHeight={height}>
    <svg>
      <!-- y axis -->
      <g class="axis y-axis" transform="translate(0,{padding.top - 8})">
        {#each yTicks as tick}
          <g
            class="tick tick-{tick}"
            transform="translate(0, {yScale(tick) - padding.bottom})">
            <line x2="100%" />
            <text y="-3">{tick}</text>
          </g>
        {/each}
      </g>

      <!-- x axis -->
      <g class="axis x-axis">
        {#each points as point, i}
          <g class="tick" transform="translate({xScale(i)},{height})">
            <text x={barWidth / 2} y="-5">{point.label}</text>
          </g>
        {/each}
      </g>

      <g class="bars">
        {#each points as point, i}
          <rect
            x={xScale(i) + 2}
            y={yScale(point.prob) - 8}
            width={barWidth - 4}
            height={height - padding.bottom - yScale(point.prob)} />
          <text
            x={xScale(i) + 30}
            y={yScale(point.prob) - 30}
            dy="1em"
            text-anchor="middle"
            fill="grey">
            {point.prob.toFixed(2)}
          </text>
        {/each}
      </g>
    </svg>
  </div>
</div>
