<script>
	import MeetupGrid from '../components/meetups/MeetupGrid.svelte';
	import getInputElement from '../helper/form.helper';
	import TextInput from '../components/ui/TextInput.svelte';
	import Button from '../components/ui/Button.svelte';
	import { initMeetups } from '../helper/mockData';

	let meetups = initMeetups;

	let title = '';
	let subtitle = '';
	let address = '';
	let imageUrl = '';
	let email = '';
	let description = '';

	function addNewMeetup() {
		const newMeetup = {
			id: Math.random().toString(),
			title,
			subtitle,
			address,
			imageUrl,
			email,
			description
		};

		meetups = [...meetups, newMeetup];
	}
</script>

<div class="flex lg:justify-center xl:justify-center sm:justify-between p-4">
	<div class="w-1/2 bg-white drop-shadow-lg lg:mx-2 sm:mx-1">
		<h1 class="text-2xl text-red-500 font-mono uppercase font-bold text-center my-5">
			Add new Meetup
		</h1>
		<form class="flex flex-col px-10 py-4" on:submit|preventDefault={addNewMeetup}>
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

			<Button type="submit" caption="Save" />
		</form>
	</div>
</div>

<MeetupGrid {meetups} />


