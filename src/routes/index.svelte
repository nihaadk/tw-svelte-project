<script>
	import AddNewMeetup from '../components/meetups/AddNewMeetup.svelte';
	import MeetupGrid from '../components/meetups/MeetupGrid.svelte';
	import { initMeetups } from '../helper/mockData';

	let meetups = initMeetups;

	function addNewMeetup(event) {
		const newMeetup = {
			...event.detail,
			id: Math.random().toString()
		};
		meetups = [...meetups, newMeetup];
	}
</script>

<AddNewMeetup on:addNewEvent={addNewMeetup} />

<MeetupGrid {meetups} />
