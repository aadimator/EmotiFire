<script>
  import Header from "./Header.svelte";
  import Hero from "./Hero.svelte";
  import Form from "./Form.svelte";
  import FAQ from "./FAQ.svelte";
  import Team from "./Team.svelte";
  import About from "./About.svelte";
  import Footer from "./Footer.svelte";
  import Result from "./Result.svelte";
  import Loader from "./Loader.svelte";
  import Feedback from "./Feedback.svelte";

  import { fade, fly } from "svelte/transition";

  let text = "";
  let result = {};
  let submited = false;
  let predictPromise;
</script>

<style global lang="postcss">
  /* only apply purgecss on utilities, per Tailwind docs */
  /* purgecss start ignore */
  @tailwind base;
  @tailwind components;
  /* purgecss end ignore */

  @tailwind utilities;
</style>

<Header />
<Hero />
<Form bind:text bind:predictPromise bind:submited />
<div id="result">
  {#await predictPromise}
    <Loader />
  {:then response}
    {#if response}
      <Result result={response} />
      <Feedback result={response} />
    {/if}
  {:catch error}
    <div
      class="relative w-full px-8 py-20 bg-yellow-400">
      <div
        class="flex max-w-sm w-full mx-auto bg-white shadow-md rounded-lg overflow-hidden"
        in:fly={{ y: 200, duration: 2000 }}
        out:fade>
        <div class="flex justify-center items-center w-12 bg-red-500">
          <svg
            class="h-6 w-6 fill-current text-white"
            viewBox="0 0 40 40"
            xmlns="http://www.w3.org/2000/svg">
            <path
              d="M20 3.36667C10.8167 3.36667 3.3667 10.8167 3.3667 20C3.3667 29.1833 10.8167 36.6333 20 36.6333C29.1834 36.6333 36.6334 29.1833 36.6334 20C36.6334 10.8167 29.1834 3.36667 20 3.36667ZM19.1334 33.3333V22.9H13.3334L21.6667 6.66667V17.1H27.25L19.1334 33.3333Z" />
          </svg>
        </div>

        <div class="-mx-3 py-2 px-4">
          <div class="mx-3">
            <span class="text-red-500 font-semibold">Error</span>
            <p class="text-gray-600 text-sm">{error.message}. Please try again later.</p>
          </div>
        </div>
      </div>
    </div>
  {/await}
  <!-- {#if result.sentiment}
    <Result bind:result />
    <Feedback bind:result />
  {:else if submited}
    <Loader />
  {/if} -->
</div>

<!-- <Feedback /> -->
<FAQ />
<!-- <Team /> -->
<About />
<Footer />
