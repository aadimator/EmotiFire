<script>
  export let selected;

  export let submitHandler = () => {};
</script>

<div class="mt-2 text-center">
  <h3 class="text-xl font-semibold leading-6 text-blue-600" id="modal-headline">
    Select an emotion
  </h3>
  <div class="mt-2">
    <p class="px-3 text-sm leading-5 text-gray-600">
      We would love to know what you think is the correct underlying emotion in
      the given text.
    </p>
  </div>
  <div class="flex flex-wrap items-center justify-center mt-2">
    <div class="flex-initial">
      <button
        class="border-none outline-none focus:border-none focus:outline-none"
        on:click={() => (selected = 'angry')}>
        <svg
          class="w-12 text-gray-600 transition-all duration-300 ease-out transform fill-current stroke-current hover:text-blue-600 hover:scale-110 {selected == 'angry' ? 'text-blue-600 scale-110' : ''}"
          viewBox="0 0 72 72"
          xmlns="http://www.w3.org/2000/svg">
          <title>Angry</title>
          <g id="line">
            <circle
              cx="36"
              cy="36"
              r="23"
              fill="none"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M28,46c1.5805-2.5575,4.9043-4.1349,8.4211-4.0038C39.6499,42.1166,42.5622,43.6595,44,46" />
            <path
              d="M30,32.9252c0,1.6567-1.3448,3-3,3c-1.6553,0-3-1.3433-3-3c0-1.6553,1.3447-3,3-3C28.6552,29.9252,30,31.27,30,32.9252" />
            <path
              d="M48,32.9252c0,1.6567-1.3447,3-3,3s-3-1.3433-3-3c0-1.6553,1.3447-3,3-3S48,31.27,48,32.9252" />
            <line
              x1="23"
              x2="30"
              y1="24"
              y2="28"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <line
              x1="49"
              x2="42"
              y1="24"
              y2="28"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
          </g>
        </svg>
      </button>
    </div>
    <div class="flex-initial">
      <button
        class="border-none outline-none focus:border-none focus:outline-none"
        on:click={() => (selected = 'negatively surprised')}>
        <svg
          class="w-12 text-gray-600 transition-all duration-300 ease-out transform fill-current stroke-current hover:text-blue-600 hover:scale-110 {selected == 'negatively surprised' ? 'text-blue-600 scale-110' : ''}"
          viewBox="0 0 72 72"
          xmlns="http://www.w3.org/2000/svg">
          <title>Negatively Surprised</title>
          <g id="line">
            <line
              x1="61.65"
              x2="57.61"
              y1="54.4498"
              y2="52.1998"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M52.4177,47.264" />
            <line
              x1="57.55"
              x2="54.34"
              y1="59.5798"
              y2="57.7998"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M46.2611,55.4728" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M55.496,60.6033" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M12.92,46.4798c0,0-0.01-0.01,0-0.01c-0.67-2.19-1.03-4.5-1.03-6.9l3.59-32.32l10.83,10.57c2.82-1.19,5.92-1.85,9.18-1.85h1.02 c3.26,0,6.36,0.66,9.18,1.85l10.83-10.57l3.59,32.32c0,2.59-0.41,5.07-1.19,7.4" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M24.7,60.5598c3.23,1.67,6.9,2.61,10.79,2.61h1.02c3.75,0,7.28-0.87,10.43-2.42" />
            <line
              x1="14.1"
              x2="10.35"
              y1="52.3598"
              y2="54.4498"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M19.5823,47.264" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M10.3474,52.3945" />
            <line
              x1="17.25"
              x2="14.45"
              y1="58.0198"
              y2="59.5798"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M25.7389,55.4728" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M16.504,60.6033" />
            <ellipse
              cx="36"
              cy="51.7194"
              rx="6.4518"
              ry="7.7514"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <ellipse
              cx="24.4558"
              cy="34.194"
              rx="7.7513"
              ry="6.4517"
              transform="matrix(0.3339 -0.9426 0.9426 0.3339 -15.9415 45.8287)"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <ellipse
              cx="46.8396"
              cy="34.1948"
              rx="6.4517"
              ry="7.7513"
              transform="matrix(0.9426 -0.3339 0.3339 0.9426 -8.7295 17.6024)"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M15.2952,65h9.0343c0,0,1.3738-13.3688,0-15.8101c-0.9984-1.7742-2.5479-5.2709-6.8527-5.1379 c-1.5576,0.0481-6.0111,1.347-4.7097,5.2514c1.8131,5.4394,3.4222,4.5051,4.2929,6.1777C18.2042,57.6789,15.2952,65,15.2952,65z" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M56.3242,65h-9.0343c0,0-1.3738-13.3688,0-15.8101c0.9984-1.7742,2.5479-5.2709,6.8527-5.1379 c1.5577,0.0481,6.0111,1.347,4.7097,5.2514c-1.8131,5.4394-3.4222,4.5051-4.2929,6.1777C53.4152,57.6789,56.3242,65,56.3242,65z" />
          </g>
        </svg>
      </button>
    </div>
    <div class="flex-initial">
      <button
        class="border-none outline-none focus:border-none focus:outline-none"
        on:click={() => (selected = 'sad')}>
        <svg
          class="w-12 text-gray-600 transition-all duration-300 ease-out transform fill-current stroke-current hover:text-blue-600 hover:scale-110 {selected == 'sad' ? 'text-blue-600 scale-110' : ''}"
          viewBox="0 0 72 72"
          xmlns="http://www.w3.org/2000/svg">
          <title>Sad</title>
          <g id="line">
            <circle
              cx="36"
              cy="36"
              r="23"
              fill="none"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              d="M30,31c0,1.6568-1.3448,3-3,3c-1.6553,0-3-1.3433-3-3c0-1.6552,1.3447-3,3-3C28.6552,28,30,29.3448,30,31" />
            <path
              d="M48,31c0,1.6568-1.3447,3-3,3s-3-1.3433-3-3c0-1.6552,1.3447-3,3-3S48,29.3448,48,31" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M28,46c1.5805-2.5575,4.9043-4.1349,8.4211-4.0038C39.6499,42.1166,42.5622,43.6595,44,46" />
          </g>
        </svg>
      </button>
    </div>
    <div class="flex-initial">
      <button
        class="border-none outline-none focus:border-none focus:outline-none"
        on:click={() => (selected = 'neutral')}>
        <svg
          class="w-12 text-gray-600 transition-all duration-300 ease-out transform fill-current stroke-current hover:text-blue-600 hover:scale-110 {selected == 'neutral' ? 'text-blue-600 scale-110' : ''}"
          viewBox="0 0 72 72"
          xmlns="http://www.w3.org/2000/svg">
          <title>Neutral</title>
          <g id="line">
            <circle
              cx="36"
              cy="36"
              r="23"
              fill="none"
              stroke-miterlimit="10"
              stroke-width="2" />
            <line
              x1="27"
              x2="45"
              y1="43"
              y2="43"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2" />
            <path
              d="M30,31c0,1.6568-1.3448,3-3,3c-1.6553,0-3-1.3433-3-3c0-1.6552,1.3447-3,3-3C28.6552,28,30,29.3448,30,31" />
            <path
              d="M48,31c0,1.6568-1.3447,3-3,3s-3-1.3433-3-3c0-1.6552,1.3447-3,3-3S48,29.3448,48,31" />
          </g>
        </svg>
      </button>
    </div>
    <div class="flex-initial">
      <button
        class="border-none outline-none focus:border-none focus:outline-none"
        on:click={() => (selected = 'happy')}>
        <svg
          class="w-12 text-gray-600 transition-all duration-300 ease-out transform fill-current stroke-current hover:text-blue-600 hover:scale-110 {selected == 'happy' ? 'text-blue-600 scale-110' : ''}"
          viewBox="0 0 72 72"
          xmlns="http://www.w3.org/2000/svg">
          <title>Happy</title>
          <g id="line">
            <circle
              cx="36"
              cy="36"
              r="23"
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M45.8147,45.2268a15.4294,15.4294,0,0,1-19.6294,0" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M31.6941,33.4036a4.7262,4.7262,0,0,0-8.6382,0" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M48.9441,33.4036a4.7262,4.7262,0,0,0-8.6382,0" />
          </g>
        </svg>
      </button>
    </div>
    <div class="flex-initial">
      <button
        class="border-none outline-none focus:border-none focus:outline-none"
        on:click={() => (selected = 'positively surprised')}>
        <svg
          class="w-12 text-gray-600 transition-all duration-300 ease-out transform fill-current stroke-current hover:text-blue-600 hover:scale-110 {selected == 'positively surprised' ? 'text-blue-600 scale-110' : ''}"
          viewBox="0 0 72 72"
          xmlns="http://www.w3.org/2000/svg">
          <title>Positively Surprised</title>
          <g id="line">
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M50.0533,44.0367" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M21.9977,44.0367" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M50.6071,41.866c0,1.6-0.29,3.11-0.87,4.49c-12.52,3.04-25.47,0.33-27.5-0.13c-0.55-1.35-0.83-2.82-0.83-4.36h0.11 c0,0,14.81,3.59,28.89,0.07L50.6071,41.866z" />
            <path
              fill="none"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M49.7371,46.356 c-1.79,4.27-6.35,7.23-13.7,7.23c-7.41,0-12.03-3.03-13.8-7.36C24.2671,46.686,37.2171,49.3959,49.7371,46.356z" />
            <path
              fill="none"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M50.2271,46.236 c-0.16,0.04-0.33,0.08-0.49,0.12" />
            <path
              fill="none"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M22.2371,46.226 c-0.19-0.05-0.28-0.07-0.28-0.07" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M46.5542,15.5591C43.3932,13.9237,39.8045,13,36,13c-3.9546,0-7.676,0.9979-10.9261,2.7556 c-0.0502,0.0271-0.1002,0.0544-0.1501,0.0819" />
            <path
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              d="M13.1945,32.9954c-0.1283,0.9833-0.1944,1.9862-0.1944,3.0046c0,12.7022,10.2969,23,23,23c12.7022,0,23-10.2978,23-23 c0-1.0073-0.0648-1.9995-0.1903-2.9726" />
            <polygon
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              points="25.1179,21.2371 33.104,20.0364 29.1993,27.1056 32.809,34.3298 24.8792,32.8007 19.124,38.4662 18.1279,30.452 10.9612,26.7292 18.2754,23.3052 19.6013,15.3389" />
            <polygon
              fill="none"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-miterlimit="10"
              stroke-width="2"
              points="46.8821,21.2371 38.896,20.0364 42.8007,27.1056 39.191,34.3298 47.1208,32.8007 52.876,38.4662 53.8721,30.452 61.0388,26.7292 53.7246,23.3052 52.3987,15.3389" />
          </g>
        </svg>
      </button>
    </div>
  </div>
</div>
<div class="px-4 py-3 sm:px-6 sm:flex sm:justify-center sm:flex-row-reverse">
  <span class="flex w-full rounded-md shadow-sm sm:ml-3 sm:w-auto">
    <button
      type="button"
      class="inline-flex justify-center w-full px-4 py-2 text-base font-medium leading-6 text-white transition duration-150 ease-in-out bg-blue-600 border border-transparent rounded-md shadow-sm hover:bg-blue-500 focus:outline-none focus:border-blue-900 focus:shadow-outline-blue sm:text-sm sm:leading-5"
      on:click={submitHandler}>
      Submit
    </button>
  </span>
</div>
