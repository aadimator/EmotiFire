<script>
  import Header from "./Header.svelte";
  import Hero from "./Hero.svelte";
  import Form from "./Form.svelte";
  import FAQ from "./FAQ.svelte";
  import Team from "./Team.svelte";
  import Footer from "./Footer.svelte";
  import Result from "./Result.svelte";



  let text = "This is a negative review. Hated the product.";
  let result = {};
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
<Form bind:text bind:result />
{#if result.sentiment}
  <Result bind:result/>
{/if}
<FAQ />
<Team />
<Footer />
