<script>
	import { onMount } from 'svelte';
	import { afterUpdate } from 'svelte';

	let showPopup = 0;
	let y = 20;
	let showedPopup = false;
	let scrolledPopup = false;

	function updateY() {
		if (y > 20) {
			y -= 10;
		} else {
			y += 10;
		}
	}

	function handleScroll() {
		const threshold = 100; // Adjust this value as needed
		if (!(window.scrollY > threshold) && !showedPopup) {
			y = 20;
			showPopup = 1;
			showedPopup = true;
		} else {
			y = 0;
			showPopup = 0;
			showedPopup = true;
		}
	}

	function scrollDown() {
		if (scrolledPopup != true) {
			scrolledPopup = true;
			window.scrollTo({
				top: 500,
				behavior: 'smooth'
			});
		}
	}

	onMount(() => {
		handleScroll();
		window.addEventListener('scroll', handleScroll);

		updateY();
		const interval = setInterval(updateY, 1000); // Update y every 1 second

		afterUpdate(() => {
			if (!showedPopup) {
				clearInterval(interval);
			}
		});

		return () => {
			window.removeEventListener('scroll', handleScroll);
			clearInterval(interval);
		};
	});
</script>

<link rel="preconnect" href="https://fonts.gstatic.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
	rel="stylesheet"
	href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
/>

<div class="popup" style="opacity: {showPopup}; bottom: {y}px;" on:click={scrollDown}>
	<span class="material-symbols-outlined">arrow_circle_down</span>
</div>

<body class="dark:bg-ctp-base light:bg-ctp-text">
	<span class="inline-block align-middle" />
	<div class="bg-ctp-blue">
		<h1>HI</h1>
	</div>
	<p class="text-ctp-text" style="padding: 20rem">hi</p>
	<div class="wave">
		<svg
			data-name="Layer 1"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 1200 120"
			preserveAspectRatio="none"
		>
			<path
				d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z"
				class="shape-fill"
			/>
		</svg>
	</div>
</body>

<style>
	@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono&display=swap');

	@tailwind base;
	@tailwind components;
	@tailwind utilities;

	body {
		display: grid;
		margin: 0rem;
	}

	p {
		@apply text-center;
	}

	h1 {
		font-family: 'JetBrains Mono';
		@apply m-8 flex place-content-center mx-auto text-center text-[100px] antialiased text-ctp-base;
		scroll-behavior: smooth;
		z-index: 10;
	}

	.popup {
		position: fixed;
		bottom: 20px;
		margin-left: 50%;
		transform: translateX(-50%);
		width: 45px;
		padding: 10px;
		@apply text-ctp-base bg-ctp-sky text-center;
		border-radius: 4px;
		box-shadow: 0px 4px 4px 0px rgba(137, 220, 235, 0.5);
		z-index: 9999;
		transition: opacity 0.5s ease-out, bottom 0.5s ease-in, width 0.5s ease-in, padding 0.5s ease-in; /* Added transition property */
	}

	.popup:hover {
		width: 100px;
		padding: 30px;
	}

	.material-symbols-outlined {
		font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 45;
	}

	.wave {
		position: absolute;
		top: 13.3rem;
		left: 0;
		width: 100%;
		overflow: hidden;
		line-height: 0;
	}

	.wave svg {
		position: relative;
		display: block;
		width: calc(100% + 1.3px);
		height: 157px;
		animation: wave-animation 25s ease-in-out infinite alternate;
	}

	@keyframes wave-animation {
		0% {
			width: calc(100% + 1px);
		}
		100% {
			width: calc(100% + 100px);
		}
	}

	.wave .shape-fill {
		fill: #89b4fa;
	}
</style>
