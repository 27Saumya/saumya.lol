<script lang="ts">
	let skills: string[] = ['Python', 'Rust', 'Typescript', 'Swift'];
</script>

<main class="flex flex-col flex-1 p-4 mt-[-12px]">
	<section id="/" class="grid grid-col-1 gap-10 py-8 sm:py-14">
		<div class="flex justify-center gap-6 md:gap-8 lg:gap-10">
			<div class="text-center">
				<h3 class="font-semibold text-4xl sm:text-5xl md:text-6xl">
					Hey <span class="wave">👋</span>! I"m <span class="gradientText">Saumya</span>,
					<br />
					a full stack <span class="gradientText">Developer</span>
				</h3>
				<br />
				<p class="sm: text-large md: text-xl">
					My proeficiency includes {#each skills as skill, index}
						<span class="gradientText">{skill}</span>{index == skills.length - 1
							? ''
							: index == skills.length - 2
								? ' & '
								: ', '}
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
				Projects that I&apos;ve <span class="gradientText font-bold">built!</span>
			</h2>
		</div>
	</section>
</main>
