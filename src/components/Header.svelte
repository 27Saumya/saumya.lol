<script lang="ts">
  import { onMount } from "svelte";

  let tabs: { name: string; link: string }[] = [
    { name: "Projects", link: "/#projects" },
    { name: "Tech Stack", link: "/#tech-stack" },
    { name: "About Me", link: "/#about" }
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
    ? 'border-b border-l-0 border-r-0 border-t-0 border-solid border-violet-400 bg-opacity-50 backdrop-blur-md backdrop-filter'
    : 'bg-transparent'} sticky top-0 z-[10] flex items-center justify-between px-6 py-4 duration-200"
>
  <h1 class="font-medium">
    <a href="/" class="duration-200 hover:text-violet-400">
      <i class="fa-solid fa-house" />
    </a>
  </h1>

  <div class="flex items-center gap-4 sm:flex-wrap sm:justify-end">
    {#each tabs as tab}
      <a href={tab.link} class="decoration-wavy duration-200 hover:text-violet-400 hover:underline">
        <p>{tab.name}</p>
      </a>
    {/each}

    <a href="http://twitter.com/saums27" target="_blank">
      <img
        class="z-[2] h-8 w-8 rounded-full border-violet-400 object-cover duration-200 hover:scale-125 hover:border-2 sm:mr-2"
        src="images/profile.png"
        alt="Saumya"
      />
    </a>
  </div>
</header>
