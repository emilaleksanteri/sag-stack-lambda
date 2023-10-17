<script lang="ts">
  import "./app.css";
  import svelteLogo from "./assets/svelte.svg";
  import router from "page";
  import Home from "./pages/Home.svelte";
  import About from "./pages/About.svelte";
  let page: any;
  let params: any;
  router("/", () => {
    page = Home;
  });
  router("/about", () => {
    page = About;
  });
  $: router.start();
</script>

<main class="w-screen flex flex-col items-center justify-center">
  <div class="flex flex-col w-screen justify-cente items-center gap-4">
    <img class="w-12 h-12" src={svelteLogo} alt="Svelte logo" />
    <ul class="flex w-full items-center justify-center text-pink-400">
      <li><a href="/">Go Home</a></li>
      <li><a href="/about">Go About</a></li>
    </ul>
  </div>
  <svelte:component this={page} {params} />
</main>
