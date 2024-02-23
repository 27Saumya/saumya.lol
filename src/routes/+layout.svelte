<script>
  import "../app.css";
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";

  let innerHeight = 0;
  let innerWidth = 0;
</script>

<div class="relative mx-auto flex min-h-screen w-full max-w-[1400px] flex-col text-sm sm:text-base">
  <Header />
  <slot />
  <Footer />
</div>

<svelte:window bind:innerHeight bind:innerWidth />
