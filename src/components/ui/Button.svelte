<script>
	export let caption;
	export let type = 'button';
	export let href = null;
	export let mode = 'btn';
</script>

{#if href}
	<a class={mode} {href}>{caption}</a>
{:else}
	<button class={mode} {type}>{caption}</button>
{/if}

<style>
	button,
	a {
		@apply bg-red-500 drop-shadow-xl inline-block  mx-2 my-2 px-4 py-2 w-full text-center text-white font-extrabold hover:text-red-100;
	}

	.outline {
		@apply bg-white drop-shadow-xl inline-block mx-2 my-2 px-4 py-2 w-full text-center text-red-500 font-extrabold hover:bg-red-500 hover:text-white;
	}
</style>
