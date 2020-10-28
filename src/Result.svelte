<script>
  import Analytics from "./Analytics.svelte";
  import BarChart from "./BarChart.svelte";
  export let result;

  const emoticons = {
    neutral: "😐",
    happy: "😀",
    angry: "😠",
    "positively surprised": "🤩",
    sad: "😥",
    "negatively surprised": "🙀",
  };

  const emotionLabels = {
    neutral: "Neutral",
    happy: "Happy",
    angry: "Angry",
    "positively surprised": "Positively Surprised",
    sad: "Sad",
    "negatively surprised": "Negatively Surprised",
  };
</script>

<div class="relative w-full px-8 py-4 bg-yellow-400 sm:py-22 md:py-20">
  <div
    class="container relative flex flex-col justify-between h-full px-8 mx-auto">
    <div class="flex flex-col justify-center w-full">
      <h2
        class="relative flex items-center self-center w-auto mb-5 text-4xl font-black">
        <span class="relative">Result</span>
      </h2>
      <div
        class="flex w-full md:w-3/4 mx-auto items-center justify-center shadow-lg  mb-4">
        <div class="w-full bg-white rounded-lg px-4 pt-2 pb-8">
          <div class="text-center w-auto mb-5" style="font-size:12rem">
            {emoticons[result.sentiment]}
          </div>
          <div class="text-center w-auto text-6xl">
            {emotionLabels[result.sentiment]}
          </div>
          <!-- {JSON.stringify(result)} -->
          <BarChart bind:probs={result.probabilities} />
        </div>
      </div>
    </div>
  </div>
</div>
