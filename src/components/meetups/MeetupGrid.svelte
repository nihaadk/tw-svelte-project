<script>
	import Card from './../ui/ Card.svelte';

	export let meetups;

	function toggleFavorite(event) {
		const { id } = event.detail;
		const updateMeetup = {...meetups.find(m => m.id === id)};
		updateMeetup.isFavorite = !updateMeetup.isFavorite;
		const meetupIndex = meetups.findIndex(m => m.id === id);
		const updateMeetups = [...meetups];
		updateMeetups[meetupIndex] = updateMeetup;
		meetups = updateMeetups;
	}
</script>

<section id="meetups" class="container mx-auto py-10">
	{#if meetups}
		<div class="flex flex-wrap m-4">
			{#each meetups as meetup}
				<div class="p-4 md:w-1/3">
					<Card {...meetup} on:toggleFavorite={toggleFavorite} />
				</div>
			{/each}
		</div>
	{:else}
		<p class="text-white font-bold text-xl text-center bg-red-400 p-10">Can not find Meetups</p>
	{/if}
</section>
