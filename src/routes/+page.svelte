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
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
	<h1>HI</h1>
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

	h1 {
		font-family: 'JetBrains Mono';
		@apply m-8 flex place-content-center text-ctp-sky mx-auto text-center text-[100px] antialiased text-transparent;
		-webkit-text-stroke: 3px #cdd6f4;
		scroll-behavior: smooth;
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
		padding: 20px;
	}

	.material-symbols-outlined {
		font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 45;
	}
</style>
