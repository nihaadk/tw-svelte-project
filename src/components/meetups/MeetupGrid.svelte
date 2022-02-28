<script>
	import Card from './../ui/ Card.svelte';
	export let meetups;
</script>

<section id="meetups" class="container mx-auto py-10">
	{#if meetups}
		<div class="flex flex-wrap m-4">
			{#each meetups as { title, subtitle, description, imageUrl, address, email }}
				<div class="p-4 md:w-1/3">
					<Card
						{title}
						{subtitle}
						{description}
						{imageUrl}
						{address}
						{email}
					/>
				</div>
			{/each}
		</div>
	{:else}
		<p class="text-white font-bold text-xl text-center bg-red-400 p-10">Can not find Meetups</p>
	{/if}
</section>
