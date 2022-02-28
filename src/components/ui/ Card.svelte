<script>
	import Button from '../ui/Button.svelte';

	export let title;
	export let subtitle;
	export let description;
	export let imageUrl;
	export let address;
	export let email;

	function log() {
		console.log('LOG DATA');
	}
</script>

<div class="max-w-md drop-shadow-xl overflow-hidden bg-white">
	<img class="w-full max-h-min" src={imageUrl} alt="cardImage" />
	<div class="px-6 py-4">
		<h1 class="text-2xl font-bold mb-2 text-red-500">{title}</h1>
		<h2 class="text-xl mb-2">{subtitle}</h2>
		<p class="text-gray-700 text-base mb-2">
			{description}
		</p>
		<p class="text-gray-700 text-base  mb-2"><span class="font-bold">Emaila:</span> {email}</p>
		<p class="text-gray-700 text-base  mb-2"><span class="font-bold">Address:</span> {address}</p>
	</div>
	<div class="px-6 pt-4 pb-2 flex">
		<Button on:click={log} caption="Contact" />
		<Button on:click={log} mode="outline" caption="Favorite" />
		<Button caption="Show Details" />
	</div>
</div>
