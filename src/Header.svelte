<!-- a little JS for the mobile nav button -->
<script>
  import { onMount } from "svelte";

  import * as animateScroll from "svelte-scrollto";

  onMount(() => {
    if (document.getElementById("nav-mobile-btn")) {
      document
        .getElementById("nav-mobile-btn")
        .addEventListener("click", function () {
          if (this.classList.contains("close")) {
            document.getElementById("nav").classList.add("hidden");
            this.classList.remove("close");
          } else {
            document.getElementById("nav").classList.remove("hidden");
            this.classList.add("close");
          }
        });
    }
  });
</script>

<style>
  /* small css for the mobile nav close */
  #nav-mobile-btn.close span:first-child {
    transform: rotate(45deg);
    top: 4px;
    position: relative;
    background: #a0aec0;
  }
  #nav-mobile-btn.close span:nth-child(2) {
    transform: rotate(-45deg);
    margin-top: 0px;
    background: #a0aec0;
  }
</style>

<div class="relative z-20 w-full h-24 px-8 pt-2 bg-white">
  <div
    class="container flex items-center justify-between h-full max-w-6xl mx-auto">
    <a href="#_" class="relative flex items-center  h-full font-black">
      <svg
        id="emoji"
        viewBox="0 0 72 72"
        xmlns="http://www.w3.org/2000/svg"
        class="w-auto h-10 mt-1">
        <g id="color">
          <circle cx="36" cy="36" r="23" fill="#FCEA2B" />
          <path
            fill="#FFFFFF"
            d="M50.595,41.64c0.012,1.5397-0.2838,3.0662-0.87,4.49c-12.49,3.03-25.43,0.34-27.49-0.13 c-0.5588-1.3852-0.8407-2.8664-0.83-4.36h0.11c0,0,14.8,3.59,28.89,0.07L50.595,41.64z" />
          <path
            fill="#EA5A47"
            d="M49.7251,46.13c-1.79,4.27-6.35,7.23-13.69,7.23c-7.41,0-12.03-3.03-13.8-7.36 C24.2951,46.47,37.235,49.16,49.7251,46.13z" />
        </g>
        <g id="hair" />
        <g id="skin" />
        <g id="skin-shadow" />
        <g id="line">
          <circle
            cx="36"
            cy="36"
            r="23"
            fill="none"
            stroke="#000000"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2" />
          <path
            fill="none"
            stroke="#000000"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M50.595,41.64 c0.012,1.5397-0.2838,3.0662-0.87,4.49c-12.49,3.03-25.43,0.34-27.49-0.13c-0.5588-1.3852-0.8407-2.8664-0.83-4.36h0.11 c0,0,14.8,3.59,28.89,0.07L50.595,41.64z" />
          <path
            fill="none"
            stroke="#000000"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M49.7251,46.13 c-1.79,4.27-6.35,7.23-13.69,7.23c-7.41,0-12.03-3.03-13.8-7.36C24.2951,46.47,37.235,49.16,49.7251,46.13z" />
          <path
            d="M30,31c0,1.6568-1.3448,3-3,3c-1.6553,0-3-1.3433-3-3c0-1.6552,1.3447-3,3-3C28.6552,28,30,29.3448,30,31" />
          <path
            d="M48,31c0,1.6568-1.3447,3-3,3s-3-1.3433-3-3c0-1.6552,1.3447-3,3-3S48,29.3448,48,31" />
        </g>
      </svg>

      <span class="ml-3 text-2xl font-black">EmotiFire</span>
    </a>

    <div
      id="nav"
      class="absolute top-0 left-0 hidden  w-full mt-20 border-b border-gray-200 sm:border-none  sm:block sm:relative sm:mt-0 sm:px-0 sm:w-auto">
      <nav
        class="flex flex-col items-center py-3 bg-white border border-gray-100 sm:flex-row sm:bg-transparent sm:border-none sm:py-0">
        <a
          href="/"
          class="relative px-1  mb-5 mr-0 text-base font-bold sm:mb-0 sm:mr-4 lg:mr-8">Home<span
            class="absolute bottom-0 left-0 w-full h-1 -mb-2 bg-yellow-300 rounded-full" /></a>
        <a
          href="#faq"
          on:click={() => animateScroll.scrollTo({ element: '#faq' })}
          class="px-1  mb-5 mr-0 text-base font-bold sm:mb-0 sm:mr-4 lg:mr-8">FAQ</a>
        <!-- <a
          href="#team"
          on:click={() => animateScroll.scrollTo({ element: '#team' })}
          class="px-1  mb-5 mr-0 text-base font-bold sm:mb-0 sm:mr-4 lg:mr-8">Team</a> -->
        <a
          href="#about"
          on:click={() => animateScroll.scrollTo({ element: '#about' })}
          class="px-1 mb-5 mr-0 text-base font-bold sm:mb-0 sm:mr-4 lg:mr-8">About</a>
      </nav>
    </div>

    <div
      id="nav-mobile-btn"
      class="absolute top-0 right-0 z-50 block w-6 mt-8 mr-10 cursor-pointer select-none sm:hidden sm:mt-10">
      <span
        class="block w-full h-1 mt-2 duration-200 transform bg-gray-800 rounded-full sm:mt-1" />
      <span
        class="block w-full h-1 mt-1 duration-200 transform bg-gray-800 rounded-full" />
    </div>
  </div>
</div>
