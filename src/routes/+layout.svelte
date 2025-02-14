<script>
  import "../app.css";
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import posthog from "posthog-js";
  import { browser } from "$app/environment";
  import { onMount } from "svelte";

  let innerHeight = 0;
  let innerWidth = 0;

  onMount(() => {
  if (browser) {
    posthog.init(
      import.meta.env.POSTHOG_KEY,
      { 
        api_host: 'https://us.i.posthog.com',
        person_profiles: 'identified_only',
      }
    )
  }
  return
});
</script>

<div class="relative mx-auto flex min-h-screen w-full max-w-[1400px] flex-col text-sm sm:text-base">
  <Header />
  <slot />
  <Footer />
</div>

<svelte:window bind:innerHeight bind:innerWidth />
