<script>
	export let value;
	export let label;
	export let id;
	export let controlTyp = 'input';
	export let type = 'text';
</script>

<div class="relative mb-4">
	<label for={id}>{label}</label>
	{#if controlTyp === 'textarea'}
		<textarea type="text" rows="3" {value} on:input />
	{:else}
		<input {type} {id} {value} on:input />
	{/if}
</div>

<style>
	label {
		@apply leading-7 text-sm text-gray-600;
	}

	input,
	textarea {
		@apply w-full bg-white border border-gray-300 text-base outline-none text-gray-700 py-1 px-3 leading-8;
	}
</style>
