<script>
  import * as animateScroll from "svelte-scrollto";

  export let text;
  export let submited;
  export let predictPromise;

  $: characters = text.length;
  $: words = text.split(" ").length;

  const submit = () => {predictPromise = doPost()};

  async function doPost() {
    animateScroll.scrollTo({ element: '#result', offset: -200})

    submited = true;
    const res = await fetch("https://backend.emotifire.com/predict", {
      method: "POST",
      body: JSON.stringify({
        text,
      }),
    });

    if (res.status === 200) {
      return await res.json();
    } else {
      throw new Error(res.statusText);
    }
  }
</script>

<div
  id="form"
  class="relative w-full px-8 py-20 bg-yellow-400 sm:py-32 md:py-40">
  <div
    class="container flex flex-col items-center justify-center h-full max-w-6xl mx-auto sm:flex-row sm:justify-between">
    <div
      class="container relative flex flex-col justify-between h-full max-w-6xl px-8 mx-auto">
      <div class="flex flex-col justify-center w-full">
        <h2
          class="relative flex items-center self-center w-auto mb-5 text-4xl font-black">
          <span
            class="absolute inline-block w-full h-4 mt-3 -ml-2 bg-yellow-400" />
          <span class="relative">Emotional Form</span>
        </h2>
        <p class="self-center mb-12 font-medium text-gray-600">
          Extract emotion from the text
        </p>
        <div
          class="flex w-full md:w-3/4 mx-auto items-center justify-center shadow-lg  mb-4 max-w-lg">
          <form
            class="w-full max-w-xl bg-white rounded-lg px-4 pt-2"
            on:submit|preventDefault={submit}>
            <div class="flex flex-wrap -mx-3 mb-6">
              <div class="w-full md:w-full px-3 mb-2 mt-2">
                <textarea
                  class="bg-gray-100 rounded border border-gray-400 leading-normal w-full h-64 py-2 px-3 font-medium placeholder-gray-700 focus:outline-none focus:bg-white"
                  name="body"
                  placeholder="Enter your Text"
                  bind:value={text}
                  required />
              </div>
              <div
                class="w-full md:w-full flex items-center justify-between px-3">
                <div class="-mr-1">
                  <input
                    type="submit"
                    class="bg-white text-gray-700 font-medium py-1 px-4 border border-gray-400 rounded-lg tracking-wide mr-1 hover:bg-gray-100"
                    value="Submit" />
                </div>
                <div>
                  <p>Word count: <span class="font-bold">{words}</span></p>
                </div>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</div>
