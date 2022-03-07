<script>
	import getInputElement from '../../helper/form.helper';
	import TextInput from '../ui/TextInput.svelte';
	import Button from '../ui/Button.svelte';
	import { createEventDispatcher } from 'svelte';

	let title = '';
	let subtitle = '';
	let address = '';
	let imageUrl = '';
	let email = '';
	let description = '';

	const dispetch = createEventDispatcher();

	function addNewMeetup() {
		dispetch('addNewEvent', {
			title,
			subtitle,
			address,
			imageUrl,
			email,
			description
		});
	}
</script>

<div class="lg:mx-2 sm:mx-1">
	<form class="flex flex-col" on:submit|preventDefault={addNewMeetup}>
		<TextInput
			id="title"
			label="Title"
			value={title}
			type="text"
			on:input={(e) => (title = getInputElement(e).value)}
		/>

		<TextInput
			id="subtitle"
			label="Subtitle"
			value={subtitle}
			on:input={(e) => (subtitle = getInputElement(e).value)}
		/>
		<TextInput
			id="address"
			label="Address"
			value={address}
			on:input={(e) => (address = getInputElement(e).value)}
		/>
		<TextInput
			id="imageUrl"
			label="Image Url"
			value={imageUrl}
			on:input={(e) => (imageUrl = getInputElement(e).value)}
		/>
		<TextInput
			id="email"
			label="E-mail"
			value={email}
			type="email"
			on:input={(e) => (email = getInputElement(e).value)}
		/>

		<TextInput
			id="description"
			label="description"
			value={description}
			controlTyp="textarea"
			on:input={(e) => (description = getInputElement(e).value)}
		/>

		<Button type="submit">Save</Button>
	</form>
</div>