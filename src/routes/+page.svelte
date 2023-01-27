<script>
	import Card from '$lib/components/Card.svelte';

	import computer from '$lib/assets/computer.png';
	import chat_bubble from '$lib/assets/chat-bubble.png';
	import travel from '$lib/assets/travel.png';

	const streakInMilliseconds = new Date().getTime() - new Date('2023-02-12').getTime();
	const streak = Math.ceil(streakInMilliseconds / (1000 * 3600 * 24));

	const name = 'Gabriel Andrade';
	let typewriter = '';

	for (let i = 0; i < name.length; i++) {
		setTimeout(() => {
			typewriter += name[i];
		}, 100 * i);
	}
</script>

<div class="text-center text-white mb-8 sm:mb-32 ">
	<div class="flex items-end justify-center">
		<span class="text-3xl sm:text-6xl mb-2 font-bold">{typewriter}</span>
		<span class="text-3xl sm:text-6xl mb-2 font-bold blink">_</span>
	</div>
	<h2 class="text-md sm:text-2xl font-semibold">Desenvolvedor ServiceNow e Front-End</h2>
</div>
<div id="cards-container" class="flex gap-4 justify-center">
	<Card>
		<img slot="image" alt="computer monitor" src={computer} class="w-28" />
		<span slot="title" class="text-2xl font-medium text-white">Estudando</span>
		<span slot="subtitle" class="text-lg text-white">SvelteKit<br />ServiceNow<br />Flutter</span>
		<h1 slot="description" class="text-white">
			Estudando para a certificação de System Administrator do ServiceNow
		</h1>
	</Card>

	<Card>
		<img slot="image" alt="computer monitor" src={travel} class="w-28" />
		<span slot="title" class="text-2xl font-medium text-white">Ocupação</span>
		<span slot="subtitle" class="text-lg text-white">Analista Desenvolvedor Jr. @ BurgerKing</span>
		<span slot="description" class="text-white">
			Time de RPA e Sutentação de Sistemas Corporativos
		</span>
	</Card>

	<Card>
		<img slot="image" alt="computer monitor" src={chat_bubble} class="w-28" />
		<span slot="title" class="text-2xl font-medium text-white">Aprendendo</span>
		<span slot="subtitle" class="text-lg text-white">Holandês</span>
		<span slot="description" class="text-white"
			><span class="text-white text-2xl">{streak}</span><br /> dias de streak no Duolingo</span
		>
	</Card>
</div>

<style lang="postcss">
	:global(html) {
		height: 100vh;

		background: linear-gradient(
			135deg,
			theme(colors.emerald.500) 0%,
			theme(colors.emerald.700) 50%,
			theme(colors.emerald.500) 100%
		);

		padding: theme(spacing.8);
	}

	:global(body) {
		height: 100%;
		width: 100%;
	}

	@media (min-width: theme(screens.sm)) {
		:global(html) {
			padding: theme(spacing.16);
		}
	}

	@media (max-width: 838px) {
		#cards-container {
			flex-direction: column;
			align-items: center;
		}
	}

	.blink {
		animation: blinking 1s step-end infinite;
		animation-delay: 1.5s;
	}

	@keyframes blinking {
		from,
		to {
			visibility: visible;
		}
		50% {
			visibility: hidden;
		}
	}
</style>
