<script lang="ts">
  import { onMount } from "svelte";
  import "iconify-icon";

  let tabs: { name: string; link: string }[] = [
    { name: "Projects", link: "#projects" },
    { name: "Tech Stack", link: "#tech-stack" },
    { name: "About Me", link: "#about" }
  ];

  let isScrolled = false;

  onMount(() => {
    window.addEventListener("scroll", handleScroll);
    return () => {
      window.removeEventListener("scroll", handleScroll);
    };
  });

  function handleScroll() {
    isScrolled = window.scrollY > 50;
  }
</script>

<header
  class="{isScrolled
    ? 'bg-opacity-50 backdrop-filter backdrop-blur-md border-b border-solid border-violet-400 border-t-0 border-r-0 border-l-0'
    : 'bg-transparent'} sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between py-5"
>
  <h1 class="font-medium">
    <a href="/" class="duration-200 hover:text-violet-400">
      <iconify-icon icon="fa:home"></iconify-icon>
    </a>
  </h1>
  <div class="sm:flex items-center gap-4 hidden">
    {#each tabs as tab, index}
      <a href={tab.link} class="duration-200 hover:underline hover:text-violet-400 decoration-wavy">
        <p>{tab.name}</p>
      </a>
    {/each}
    <a href="http://twitter.com/saums27" target="_blank">
      <img class="w-8 h-8 rounded-full object-cover z-[2]" src="images/profile.png" alt="Saumya" />
    </a>
  </div>
</header>
