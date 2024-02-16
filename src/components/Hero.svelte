<script lang="ts">
  let skills: string[] = ["Python", "Rust", "Typescript", "Swift"];
  let projects: {
    title: string;
    description: string;
    image: string;
    githubLink: string | undefined;
  }[] = [
    {
      title: "Macboard",
      description: "A minimalistic clipboard Manager for macOS",
      image: "project-assets/macboard.png",
      githubLink: "https://github.com/27Saumya/Macboard"
    },
    {
      title: "Yuki",
      description: "A fun, cute & multipurpose discord bot",
      image: "project-assets/yuki.png",
      githubLink: "https://github.com/27Saumya/Macboard"
    },
    {
      title: "Create Discord Bot",
      description: "A blazingly fast 🚀 CLI tool for quickly creating Discord Bot boilerplates",
      image: "project-assets/create-discord-bot.png",
      githubLink: "https://github/27Saumya/create-discord-bot"
    }
  ];
</script>

<main class="flex flex-col flex-1 p-4 mt-[-12px]">
  <section id="/" class="grid grid-col-1 gap-10 py-8 sm:py-14">
    <div class="flex justify-center gap-6 md:gap-8 lg:gap-10">
      <div class="text-center">
        <h3 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
          Hey <span class="wave">👋</span>! I&apos;m <span class="gradientText">Saumya</span>&comma;
          <br />
          a full stack <span class="gradientText">Developer</span>
        </h3>
        <br />
        <p class="sm: text-large md: text-xl">
          My proeficiency includes {#each skills as skill, index}
            <span class="gradientText">{skill}</span>{index == skills.length - 1
              ? ""
              : index == skills.length - 2
                ? " & "
                : ", "}
          {/each}
        </p>
      </div>
    </div>
    <img
      src="images/profile.png"
      alt="Profile"
      class="rounded-full object-cover z-[2] max-h-[70vh] mx-auto mt-8"
    />
  </section>

  <section id="projects" class="py-20 lg:py-32 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center">
      <h2 class="Poppins text-lg sm:text-xl lg:text-2xl">
        Projects that I&apos;ve <span class="gradientText font-bold">built</span> with
        <span class="wave">💖</span>
      </h2>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each projects as project}
        <div
          class="border rounded-[20px] border-violet-400 overflow-hidden hover:shadow-lg transition duration-300 ease-in-out"
        >
          <img src={project.image} alt={project.title} class="w-full h-64 object-cover" />

          <div class="p-4">
            <a href={project.githubLink} class="duration-200">
              <h3 class="gradientText text-center font-bold text-xl mb-2">{project.title}</h3>
            </a>
            <p class="text-center">{project.description}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>
</main>
