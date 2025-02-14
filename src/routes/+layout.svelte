<script lang="ts">
  import "../app.css";
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";
  import { browser } from "$app/environment";
  import posthog from "posthog-js";
  import { PUBLIC_POSTHOG_KEY } from "$env/static/public";

  if (browser) {
    posthog.init(PUBLIC_POSTHOG_KEY, {
      api_host: "https://us.i.posthog.com"
    });
  }

  let innerHeight = 0;
  let innerWidth = 0;
</script>

<div class="relative mx-auto flex min-h-screen w-full max-w-[1400px] flex-col text-sm sm:text-base">
  <Header />
  <slot />
  <Footer />
</div>

<svelte:window bind:innerHeight bind:innerWidth />
