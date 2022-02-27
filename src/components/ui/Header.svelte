<script>
	let navItems = [
		{
			name: 'Home',
			link: '/'
		},
		{
			name: 'About',
			link: '/about'
		}
	];
</script>

<header class="text-white body-font drop-shadow-xl bg-red-600">
	<div class="nav-container">
		<a href="/" class="nav-logo">
			<span class="logo">MeetUp</span>
		</a>
		<nav class="nav-list">
			{#each navItems as { name, link }}
				<a href={link} class="nav-item">{name}</a>
			{/each}
		</nav>
	</div>
</header>

<style>
	.nav-container {
		@apply container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center;
	}

	.nav-logo {
		@apply flex font-medium items-center text-gray-900 mb-4 md:mb-0;
	}

	.logo {
		@apply ml-3 text-2xl font-bold text-white;
	}

	.nav-list {
		@apply md:ml-auto flex flex-wrap items-center text-base justify-center;
	}

	.nav-item {
		@apply mr-5 hover:text-white;
	}
</style>
