<div class="u-container h-[390px] w-[258px] rounded-xl border-transparent border ">
	<div class="h-2/3 flex flex-col items-center justify-top p-2">
		<div class="flex flex-col items-center">
			<slot name="image" />
			<slot name="title" />
		</div>
		<div class="flex flex-col items-center flex-grow justify-center text-center">
			<slot name="subtitle" />
		</div>
	</div>
	<div class="h-1/3 flex flex-col items-center justify-center p-2 text-center">
		<slot name="description" />
	</div>
</div>

<style lang="postcss">
	.u-container {
		background-repeat: no-repeat;

		background-image: linear-gradient(
				135deg,
				rgba(250, 250, 250, 0.1) 0%,
				theme(colors.emerald.500) 100%
			),
			linear-gradient(135deg, rgba(250, 250, 250, 0.1) 0%, theme(colors.emerald.500) 100%);

		background-position: 0 0, 0 100%;

		background-size: 100% 66.66666%, 100% 33.33333%;
	}

	@media (max-width: 838px) {
		.u-container {
			width: 100%;
		}
	}
</style>
