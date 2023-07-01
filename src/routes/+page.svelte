<link rel="preconnect" href="https://fonts.gstatic.com" />
<body>
	<span class="inline-block align-middle" />
	<h1>HI</h1>
</body>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

	@tailwind base;
	@tailwind components;
	@tailwind utilities;

	body {
		@apply bg-ctp-base;
	}

	h1 {
		font-family: 'Poppins', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
			Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		@apply m-8 flex place-content-center text-ctp-sky mx-auto text-center text-[100px] antialiased text-transparent;
		-webkit-text-stroke: 3px #cdd6f4;
	}
</style>
