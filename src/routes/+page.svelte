<body>
	<h1>hi</h1>
</body>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Noto+Sans&display=swap');

	@tailwind base;
	@tailwind components;
	@tailwind utilities;

	body {
		@apply bg-ctp-base;
	}

	h1 {
		font-family: 'Noto sans';
		@apply m-8 text-ctp-sky mx-auto text-center text-[50px] antialiased;
	}
</style>
