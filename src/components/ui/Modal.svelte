<script>
	export let title = 'New Meetups';
</script>

<div class="fixed inset-0 m-0 p-0 bg-gray-900 bg-opacity-90 transition-opacity z-10">
	<div
		class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0"
	>
		<div
			class="relative inline-block align-bottom bg-white text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full"
		>
			<div class="bg-white px-4 pt-5 pb-4 sm:p-6 sm:pb-4">
				<div class="mt-3 text-center">
                    <h3 class="text-2xl leading-6 font-medium text-gray-900 text-center">
                        {title}
                    </h3>
                    <div class="mt-2">
                        <slot />
                    </div>
                </div>
			</div>
		</div>
	</div>
</div>
