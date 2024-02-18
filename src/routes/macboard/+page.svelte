<script lang="ts">
  import Card from "../../components/Card.svelte";

  let features: {
    title: string;
    description: string;
    image: string;
  }[] = [
    {
      title: "CLEAN UI",
      description:
        "What is important for an app to be classified as a minimal one? Undoubtebly the UI, and likewise Macboard has a very clean UI for the best user experience!",
      image: "project-assets/sidebar.svg"
    },
    {
      title: "LIGHTWEIGHT",
      description:
        "Experience unparalleled speed and efficiency with our lightweight design, ensuring smooth performance even on resource-constrained devices.",
      image: "project-assets/feather.svg"
    },
    {
      title: "DETAILS",
      description:
        "Get details for any and everything you copy, Macboard offers users to view the time since something was copied, the app from which it was copied and even URL previews!",
      image: "project-assets/info.svg"
    },
    {
      title: "KEYBOARD CONTROL",
      description:
        "Take full control of your workflow with intuitive keyboard shortcuts and navigation, allowing you to accomplish tasks with minimal hand movement.",
      image: "project-assets/keyboard.svg"
    },
    {
      title: "SECURE & PRIVATE",
      description:
        "Macboard respects your privacy and security the most. You don't have to worry about your data, all of this is stored right on your computer.",
      image: "project-assets/lock.svg"
    },
    {
      title: "OPEN SOURCE",
      description:
        "Macboard is completely open source! Meaning, anyone can contribute to add new features, fix bugs, etc. This also makes updates quite more often!",
      image: "project-assets/github.svg"
    }
  ];
</script>

<svelte:head>
  <title>Macboard</title>
  <meta property="og:title" content="Macboard" />
  <meta property="og:description" content="A minimalistic clipboard manager for macOS" />
  <meta property="og:image" content="project-assets/macboard.png" />
  <meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<main class="flex flex-col flex-1 p-4 mt-[-12px]">
  <section class="flex flex-wrap justify-center items-center py-8 sm:py-14">
    <img src="project-assets/macboard.png" alt="Macboard Logo" class="w-32 h-32 mr-4" />
    <div class="text-center md:text-left">
      <h3 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
        <span class="gradientText">Macboard</span>
      </h3>
      <p class="mt-3 sm:text-large md:text-xl">
        A <span class="gradientText">minimalistic</span> clipboard manager for macOS
      </p>
    </div>
    <br />
  </section>
  <section class="flex flex-row justify-center items-center mt-[-20px]">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div
      on:click={() =>
        window.open(
          "http://github.com/27Saumya/Macboard/releases/latest/download/Macboard.dmg",
          "_blank"
        )}
      class="Poppins poppingButton cursor-pointer font-bold text-lg rounded-xl px-5 py-2 text-center me-3 mb-2 text-white bg-gradient-to-r from-[#b385f4] to-[#4f48dd] hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-purple-300 dark:focus:ring-purple-800"
    >
      <i class="fa fa-download" />&nbsp; Download
    </div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div
      on:click={() => window.open("http://github.com/27Saumya/Macboard", "_blank")}
      class="Poppins poppingButton cursor-pointer border-2 border-violet-600 font-bold text-lg rounded-2xl px-5 py-2 text-center me-3 mb-2 text-white hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-purple-300 dark:focus:ring-purple-800"
    >
      <i class="fa fa-github" />&nbsp; Github
    </div>
  </section>
  <p class="text-center">
    <i class="fa-brands fa-apple" />&nbsp; MacOS Ventura 13.0+
  </p>

  <section class="py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center">
      <h2 class="Poppins text-3xl">
        Why <span class="Poppins gradientText text-4xl font-bold">use</span> Macboard?
      </h2>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each features as card}
        <Card classes="aspect-[1] lg:w-[350px] ">
          <div
            class="content flex gap-3 p-1 items-center text-center justify-center flex-col max-w-[20rem]"
          >
            <div
              class="bg-[#9792ff] p-5 flex rounded-xl border border-outline border-violet-400 justify-center items-center aspect-[1]"
            >
              <img src={card.image} alt={card.title} class="w-10" />
            </div>
            <div class="">
              <h1 class="gradientText pl-2 text-2xl font-semibold">
                {card.title}
              </h1>
              <p class="pl-2 mt-1 text-sm opacity-[0.8]">
                {card.description}
              </p>
            </div>
          </div>
        </Card>
      {/each}
    </div>
  </section>
</main>
