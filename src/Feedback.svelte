<script>
  import EmotionFeedback from "./EmotionFeedback.svelte";
  import { fade, fly } from "svelte/transition";

  export let result;
  let sentiment = result.sentiment;
  let feedback_submitted = false;
  let show_emotions = false;

  async function submitFeedback() {
    feedback_submitted = true;
    const res = await fetch("http://34.122.67.36:8000/feedback", {
      method: "POST",
      body: JSON.stringify({
        textId: result.firebaseId,
        sentiment: sentiment,
      }),
    });
  }
</script>

<div
  id="feedback"
  class="relative w-full px-8 py-4 bg-yellow-400 sm:py-22 md:py-20">
  <div
    class="container relative flex flex-col justify-between h-full px-8 mx-auto">
    <div class="flex flex-col justify-center w-full">
      <h2
        class="relative flex items-center self-center w-auto mb-5 text-4xl font-black">
        <span class="relative">Feedback</span>
      </h2>

      {#if feedback_submitted}
        <div
          class="flex max-w-sm w-full mx-auto bg-white shadow-md rounded-lg overflow-hidden"
          in:fly={{ y: 200, duration: 2000 }}
          out:fade>
          <div class="flex justify-center items-center w-12 bg-green-500">
            <svg
              class="h-6 w-6 fill-current text-white"
              viewBox="0 0 40 40"
              xmlns="http://www.w3.org/2000/svg">
              <path
                d="M20 3.33331C10.8 3.33331 3.33337 10.8 3.33337 20C3.33337 29.2 10.8 36.6666 20 36.6666C29.2 36.6666 36.6667 29.2 36.6667 20C36.6667 10.8 29.2 3.33331 20 3.33331ZM16.6667 28.3333L8.33337 20L10.6834 17.65L16.6667 23.6166L29.3167 10.9666L31.6667 13.3333L16.6667 28.3333Z" />
            </svg>
          </div>

          <div class="-mx-3 py-2 px-4">
            <div class="mx-3">
              <span class="text-green-500 font-semibold">Success</span>
              <p class="text-gray-600 text-sm">
                Thank you for submitting your feedback!
              </p>
            </div>
          </div>
        </div>
      {:else}
        <div
          class="flex w-full md:w-3/4 mx-auto items-center justify-center shadow-lg  mb-4"
          in:fade
          out:fly={{ y: 200, duration: 1000 }}>
          <div class="w-full bg-white rounded-lg px-4 py-8">
            <div class="text-center w-auto text-3xl">
              Do you agree with the prediction?
            </div>
            <div class="flex justify-center px-8 py-8">
              <button
                class="mx-8 px-8 py-3 mb-1 mr-1 font-bold text-green-600 uppercase transition-all duration-300 ease-in-out bg-transparent border border-green-600 border-solid rounded-md outline-none hover:bg-green-600 hover:text-white active:bg-blue-600 focus:outline-none"
                type="button"
                on:click={submitFeedback}>
                Absolutely 👍
              </button>

              <button
                class="mx-8 px-8 py-3 mb-1 mr-1 font-bold text-blue-600 uppercase transition-all duration-300 ease-in-out bg-transparent border border-blue-600 border-solid rounded-md outline-none hover:bg-blue-600 hover:text-white active:bg-blue-600 focus:outline-none"
                type="button"
                on:click={() => (show_emotions = true)}>
                Not at all 👎
              </button>
            </div>
            {#if show_emotions}
              <EmotionFeedback
                submitHandler={submitFeedback}
                bind:selected={sentiment} />
            {/if}
          </div>
        </div>
      {/if}
    </div>
  </div>
</div>
