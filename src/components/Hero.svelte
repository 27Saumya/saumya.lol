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
      image: "project-assets/macboard-full.png",
      link: "/macboard"
    },
    {
      title: "Cricket Guru",
      description:
        "Relive your favorite sport through the best cricket bot on Discord with 33K+ users & 14K+ servers (co-developer)",
      image: "project-assets/cg.png",
      link: "https://cricketguru.live"
    },
    {
      title: "Lines Tally",
      description: "An elegant CLI tool that returns the number of lines of code in a directory",
      image: "project-assets/lines-tally.png",
      link: "https://github.com/27Saumya/lines-tally"
    },
    {
      title: "Create Discord Bot",
      description: "A blazingly fast 🚀 CLI tool for quickly creating Discord Bot boilerplates",
      image: "project-assets/create-discord-bot.png",
      link: "https://github.com/27Saumya/create-discord-bot"
    },
    {
      title: "Hangdev",
      description:
        "A CLI game inspired from Hangman made for developers to play right in their computer shell!",
      image: "project-assets/hangdev.png",
      link: "https://github.com/27Saumya/hangdev"
    },
    {
      title: "Cookin'",
      description: "Cookin' something hard, please lemme cook now!",
      image: "project-assets/cookin.png",
      link: "https://github.com/27Saumya"
    }
  ];

  let techStackCards: {
    title: string;
    description: string;
    image: string;
    link: string;
    tag: string;
  }[] = [
    {
      title: "Python",
      description:
        "Python is a versatile and powerful programming language used for web development, data science, artificial intelligence, and more.",
      image: "tech-stack/python.svg",
      link: "https://python.org",
      tag: "Language"
    },
    {
      title: "Rust",
      description:
        "Rust is a systems programming language that offers memory safety, concurrency, and performance. It is suitable for building high-performance and reliable software.",
      image: "tech-stack/rust.svg",
      link: "https://www.rust-lang.org/",
      tag: "Language"
    },
    {
      title: "TypeScript",
      description:
        "TypeScript is a superset of JavaScript that adds static typing and other features to enhance developer productivity and code quality.",
      image: "tech-stack/ts.svg",
      link: "https://www.typescriptlang.org/",
      tag: "Language"
    },
    {
      title: "Swift",
      description:
        "Swift is a powerful and intuitive programming language for macOS, iOS, watchOS, and tvOS development. It offers modern features and performance.",
      image: "tech-stack/swift.svg",
      link: "https://developer.apple.com/swift/",
      tag: "Language"
    },
    {
      title: "React",
      description:
        "ReactJS is a JavaScript library for building user interfaces. It is maintained by Facebook and offers a component-based approach for building reusable UI components.",
      image: "tech-stack/react.svg",
      link: "https://reactjs.org/",
      tag: "Library"
    },
    {
      title: "Next.js",
      description:
        "Next.js is a React framework for building server-rendered and statically-generated web applications. It offers features like automatic code splitting, server-side rendering, and more.",
      image: "tech-stack/next.svg",
      link: "https://nextjs.org/",
      tag: "Framework"
    },
    {
      title: "Svelte",
      description:
        "Svelte is a radical new approach to building user interfaces. It shifts the work from the browser to the build step, resulting in highly optimized and efficient applications.",
      image: "tech-stack/svelte.svg",
      link: "https://svelte.dev/",
      tag: "Framework"
    },
    {
      title: "SvelteKit",
      description:
        "SvelteKit is a framework for building web applications with Svelte. It provides tools and conventions for routing, server-side rendering, and more to streamline development.",
      image: "tech-stack/svelte.svg",
      link: "https://kit.svelte.dev/",
      tag: "Framework"
    },
    {
      title: "Tailwind CSS",
      description:
        "Tailwind CSS is a utility-first CSS framework for building custom designs without having to leave your HTML. It offers a low-level utility approach for styling web applications.",
      image: "tech-stack/tailwind.svg",
      link: "https://tailwindcss.com/",
      tag: "Framework"
    },
    {
      title: "PostgreSQL",
      description:
        "PostgreSQL is a powerful, open-source relational database system known for its reliability, feature-richness, and robustness. It is widely used in enterprise applications.",
      image: "tech-stack/postgresql.svg",
      link: "https://www.postgresql.org/",
      tag: "Database"
    },
    {
      title: "MongoDB",
      description:
        "MongoDB is a popular NoSQL database known for its flexibility, scalability, and performance. It stores data in flexible, JSON-like documents.",
      image: "tech-stack/mongodb.svg",
      link: "https://www.mongodb.com/",
      tag: "Database"
    },
    {
      title: "Git",
      description:
        "Git is a distributed version control system for tracking changes in source code during software development.",
      image: "tech-stack/git.svg",
      link: "https://git-scm.com/",
      tag: "Version Control"
    }
  ];
</script>

<main class="flex flex-col flex-1 p-4 mt-[-12px]">
  <section
    id="/"
    class="grid grid-col-1 gap-10 py-8 sm:py-14"
    style="text-shadow: 0px 0px 100px white;"
  >
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
      <h2
        class="Poppins text-lg sm:text-xl lg:text-2xl underline decoration-wavy decoration-violet-400"
      >
        Projects that I&apos;ve <span class="gradientText font-bold">built</span> with 💖
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

  <section id="tech-stack" class="py-16 flex flex-col gap-24">
    <div class="flex flex-col gap-2 text-center">
      <h2
        class="Poppins text-lg sm:text-xl lg:text-2xl underline decoration-wavy decoration-violet-400"
      >
        Tech I <span class="gradientText text-2xl font-bold">use</span> everyday 👨‍💻
      </h2>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each techStackCards as card}
        <Card
          on:click={() => window.open(card.link, "_blank")}
          classes="cursor-pointer aspect-[1] lg:w-[350px] "
        >
          <div
            class="content flex gap-3 p-1 items-center text-center justify-center flex-col max-w-[20rem]"
          >
            <div
              class="bg-[#3d3a45] p-5 flex rounded-xl border border-outline border-violet-400 justify-center items-center aspect-[1]"
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
              <div class="flex justify-center items-center flex-wrap gap-1">
                <div
                  class="gradientText rounded-xl border border-indigo-700 font-semibold text-sx px-2 py-1 mt-4"
                >
                  {card.tag}
                </div>
              </div>
            </div>
          </div>
        </Card>
      {/each}
    </div>
  </section>

  <section id="about" class="py-16 text-center">
    <h2
      class="Poppins text-lg sm:text-xl lg:text-2xl underline decoration-wavy decoration-violet-400"
    >
      A little more <span class="gradientText font-bold">about</span> me 🤭
    </h2>
    <p class="sm:px-4 md:px-8 lg:px-20 mt-4 text-pretty">
      Hey there, thanks for sticking out till the very end! Let me tell you more about myself.<br />
      I am Saumya&comma; a young passionate&comma; self taught developer from India&comma; always trying
      to stay engaged in a project&comma; trying to improve my skills furtermore!<br />
      I love <span class="gradientText underline decoration-wavy">geography</span>&comma;
      <span class="gradientText underline">rubik&apos;s cubes</span>&comma; and
      <span class="gradientText">music</span> alongside programming!
    </p>
  </section>
</main>
