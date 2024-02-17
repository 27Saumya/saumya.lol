<script lang="ts">
  import Card from "./Card.svelte";

  let skills: { name: string; link: string }[] = [
    {
      name: "Python",
      link: "https://www.python.org"
    },
    {
      name: "Rust",
      link: "https://www.rust-lang.org"
    },
    {
      name: "Typescript",
      link: "https://www.typescriptlang.org"
    },
    {
      name: "Swift",
      link: "https://www.swift.org"
    }
  ];

  let projects: {
    title: string;
    description: string;
    image: string;
    link: string;
  }[] = [
    {
      title: "Macboard",
      description: "A minimalistic clipboard Manager for macOS",
      image: "project-assets/macboard.png",
      link: "https://github.com/27Saumya/Macboard"
    },
    {
      title: "Cricket Guru",
      description: "Relive your favorite sport through the best cricket bot on Discord with 33K+ users & 14K+ servers (co-developer)",
      image: "project-assets/cg.png",
      link: "https://github.com/27Saumya/lines-tally"
    },
    {
      title: "Create Discord Bot",
      description: "A blazingly fast 🚀 CLI tool for quickly creating Discord Bot boilerplates",
      image: "project-assets/create-discord-bot.png",
      link: "https://github.com/27Saumya/create-discord-bot"
    },
    {
      title: "Lines Tally",
      description: "An elegant CLI tool that returns the number of lines of code in a directory",
      image: "project-assets/lines-tally.png",
      link: "https://github.com/27Saumya/lines-tally"
    },
    {
      title: "Hangdev",
      description: "A CLI game inspired from Hangman made for developers to play right in their computer shell!",
      image: "project-assets/hangdev.png",
      link: "https://github.com/27Saumya/hangdev"
    },
    {
      title: "Yuki",
      description: "A fun, cute & multipurpose discord bot (no longer available 😔)",
      image: "project-assets/yuki.png",
      link: "https://github.com/27Saumya/Yuki"
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
            <span class="gradientText hover:underline hover:decoration-wavy decoration-violet-400"
              ><a href={skill.link} target="_blank">{skill.name}</a></span
            >{index == skills.length - 1 ? "" : index == skills.length - 2 ? " & " : ", "}
          {/each}
        </p>
      </div>
    </div>
    <img
      src="images/profile.png"
      alt="Profile"
      class="border-4 border-violet-400 rounded-full object-cover z-[2] max-h-[70vh] mx-auto mt-8"
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
        <Card>
          <div
            class="content flex gap-3 p-1 items-start text-left justify-center flex-col max-w-[20rem]"
          >
            <a href={project.link} target="_blank">
              <img src={project.image} alt={project.title} class=" object-cover rounded-3xl" />
            </a>
            <div class="">
              <a
                href={project.link}
                target="_blank"
                class="gradientText pl-2 text-2xl font-semibold underline decoration-transparent underline-offset-4 hover:decoration-violet-400"
              >
                {project.title}
              </a>
              <p class="pl-2 mt-1 text-sm opacity-[0.8]">
                {project.description}
              </p>
            </div>
          </div>
        </Card>
      {/each}
    </div>
  </section>
</main>
