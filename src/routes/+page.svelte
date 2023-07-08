<script lang="ts">
  import Hackerman from '../components/hackerman.svelte';
  import Wave from '../components/wave.svelte';
  import Font from '../components/fonts.svelte'
  import Popup from '../components/popup.svelte'
  import Lorem from '../components/lorem.svelte'
</script>

<Popup />

<Font />

<Hackerman />

<body class="dark:bg-ctp-base light:bg-ctp-text">
  <div class="bg-ctp-blue">
    <img src="/matej-rieciciar-SdDvoAvu384-unsplash.jpg" class="w-24 h-24 md:w-48 md:h-48 rounded-full m-8 flex place-content-center mx-auto text-center" style="z-index: 9999;" alt="" width="384" height="384"> 
    <div class="container">
      <h1 data-value="HI" class="m-8 w-10 text-center text-[100px] antialiased text-ctp-base">HI</h1>
    </div>
  </div>
  <Wave />
  <Lorem />
</body>

<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono&display=swap');

  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  body {
    display: grid;
    margin: 0rem;
    font-family: 'JetBrains Mono', monospace;
  }

  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    margin-left: 50%;
    transform: translateX(-50%);
  }

  h1 {
    @apply text-center;
    width: 150px;
    scroll-behavior: smooth;
  }
</style>
