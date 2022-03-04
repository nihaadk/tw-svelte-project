<script>
	export let type = 'button';
	export let href = null;
	export let mode = 'btn';
	export let color = null;
</script>

{#if href}
	<a on:click class={mode} {href}><slot /></a>
{:else}
	<button on:click class="{mode} {color}" {type}>
		<slot />
	</button>
{/if}

<style>
	button,
	a {
		@apply bg-red-500 drop-shadow-xl inline-block  mx-2 my-2 px-4 py-2 w-full text-center text-white font-extrabold hover:text-red-100;
	}

	.outline {
		@apply bg-white drop-shadow-xl inline-block mx-2 my-2 px-4 py-2 w-full text-center text-red-500 font-extrabold hover:bg-red-500 hover:text-white;
	}

	.success {
		@apply bg-green-500 text-white hover:bg-green-700;
	}
</style>
