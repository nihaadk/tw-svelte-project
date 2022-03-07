<script>
	import AddNewMeetup from '../components/meetups/AddNewMeetup.svelte';
	import MeetupGrid from '../components/meetups/MeetupGrid.svelte';
	import Button from './../components/ui/Button.svelte';
	import Modal from './../components/ui/Modal.svelte';
	import { initMeetups } from '../helper/mockData';

	let meetups = initMeetups;
	let editMode;

	function addNewMeetup(event) {
		const newMeetup = {
			...event.detail,
			isFavorite: false,
			id: Math.random().toString()
		};
		meetups = [...meetups, newMeetup];
		editMode = null;
	}
</script>

{#if !editMode}
	<Button on:click={() => (editMode = 'add')}>Add New Meetups</Button>
{/if}

{#if editMode === 'add'}
	<Modal>
		<AddNewMeetup on:addNewEvent={addNewMeetup} />
	</Modal>
	
{/if}

<MeetupGrid {meetups} />
