<script>
	import { onMount } from 'svelte';

	let showPopup = 0;
	let y = 20;
	let showedPopup = false;

	async function forY() {
		try {
			while (true) {
				if (y > 20) {
					y = y - 5;
				} else {
					y = y + 5;
				}
				await new Promise((resolve) => setTimeout(resolve, 1000)); // Wait for 1 second before repeating the loop
			}
		} catch (err) {
			console.error(err);
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

	onMount(() => {
		forY();
		handleScroll();
		window.addEventListener('scroll', handleScroll);
	});
</script>

<div class="popup" style="opacity: {showPopup}; bottom: {y}px;">Scroll down</div>

<link rel="preconnect" href="https://fonts.gstatic.com" />
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
	@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

	@tailwind base;
	@tailwind components;
	@tailwind utilities;

	h1 {
		font-family: 'Poppins', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
			Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		@apply m-8 flex place-content-center text-ctp-sky mx-auto text-center text-[100px] antialiased text-transparent;
		-webkit-text-stroke: 3px #cdd6f4;
		scroll-behavior: smooth;
	}

	.popup {
		position: fixed;
		bottom: 20px;
		left: 50%;
		transform: translateX(-50%);
		padding: 10px;
		@apply bg-ctp-base text-ctp-sky;
		border-radius: 4px;
		box-shadow: 0 4px 4px #11111b;
		z-index: 9999;
		transition: opacity 0.5s ease-out, bottom 0.5s ease-out; /* Added transition property */
		pointer-events: none; /* Disable pointer events */
	}
</style>
