<script lang="ts">
	import 'iconify-icon';
	let tabs: { name: string; link: string }[] = [
		{ name: 'Projects', link: '#projects' },
		{ name: 'About Me', link: '#about' }
	];
</script>

<header
	class="sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border border-solid py-5 bg-transparent border-transparent"
>
	<h1 class="font-medium">
		<a href="/" class="duration-200 hover:text-violet-400">
			<iconify-icon icon="fa:home"></iconify-icon>
		</a>
	</h1>
	<div class="sm:flex items-center gap-4 hidden">
		{#each tabs as tab, index}
			<a href={tab.link} class="duration-200 hover:text-violet-400">
				<p>{tab.name}</p>
			</a>
		{/each}
	</div>
</header>
