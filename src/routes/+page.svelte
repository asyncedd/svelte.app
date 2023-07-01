<script>
	import { onMount } from 'svelte';

	let showPopup = false;
	let showedPopup = false;

	function handleScroll() {
		const threshold = 100; // Adjust this value as needed
		if (!(window.scrollY > threshold) && !showedPopup) {
			showPopup = true;
			showedPopup = true;
		} else {
			showPopup = false;
			showedPopup = true;
		}
	}

	onMount(() => {
		handleScroll();
		window.addEventListener('scroll', handleScroll);
	});
</script>

{#if showPopup}
	<div class="popup show">Scroll down</div>
{/if}

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
		opacity: 1; /* Hide the popup */
		transition: opacity 0.5s ease-out; /* Added transition property */
	}

	.popup:not(.show) {
		opacity: 0; /* Hide the popup */
		pointer-events: none; /* Disable pointer events */
	}
</style>
