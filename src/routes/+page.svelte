<script lang="ts">
  import Hackerman from '../components/hackerman.svelte';
  import Wave from '../components/wave.svelte';
  import { onMount, afterUpdate } from 'svelte';

  let showPopup: number = 0;
  let y: number = 20;
  let showedPopup: boolean = false;
  let scrolledPopup: boolean = false;

  function updateY(): void {
    if (y > 20) {
      y -= 10;
    } else {
      y += 10;
    }
  }

  function handleScroll(): void {
    const threshold: number = 100; // Adjust this value as needed
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

  function scrollDown(): void {
    if (scrolledPopup !== true) {
      scrolledPopup = true;
      window.scrollTo({
        top: 500,
        behavior: 'smooth',
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

<Hackerman />

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
  <div class="bg-ctp-blue">
    <img src="/matej-rieciciar-SdDvoAvu384-unsplash.jpg" class="w-24 h-24 md:w-48 md:h-48 rounded-full m-8 flex place-content-center mx-auto text-center" style="z-index: 9999;" alt="" width="384" height="384"> 
    <div class="container">
      <h1 data-value="HI" class="m-8 w-10 text-center text-[100px] antialiased text-ctp-base">HI</h1>
    </div>
  </div>
  <p class="text-ctp-text" style="padding: 20rem">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Habitant morbi tristique senectus et netus et malesuada fames ac. Donec et odio pellentesque diam volutpat commodo sed egestas egestas. Quam vulputate dignissim suspendisse in est ante in nibh mauris. Tempus quam pellentesque nec nam. Risus at ultrices mi tempus imperdiet nulla malesuada. Dui nunc mattis enim ut tellus elementum sagittis vitae et. Pellentesque elit ullamcorper dignissim cras. Ut aliquam purus sit amet. Platea dictumst vestibulum rhoncus est pellentesque elit ullamcorper dignissim. Donec ac odio tempor orci. Sit amet volutpat consequat mauris nunc congue. Ipsum dolor sit amet consectetur adipiscing elit. Mauris sit amet massa vitae tortor condimentum lacinia quis. Elementum eu facilisis sed odio morbi quis. Euismod elementum nisi quis eleifend quam adipiscing.

    Risus nec feugiat in fermentum. Tincidunt id aliquet risus feugiat in. Egestas sed sed risus pretium quam vulputate. Id eu nisl nunc mi ipsum faucibus vitae aliquet. In vitae turpis massa sed elementum tempus egestas sed sed. Non diam phasellus vestibulum lorem sed risus ultricies tristique nulla. Tempus imperdiet nulla malesuada pellentesque elit eget gravida cum. Ultrices mi tempus imperdiet nulla malesuada pellentesque elit. Vel elit scelerisque mauris pellentesque pulvinar pellentesque. Enim ut sem viverra aliquet eget sit amet tellus. Dui nunc mattis enim ut tellus elementum sagittis. Fermentum iaculis eu non diam phasellus vestibulum. Nam libero justo laoreet sit amet cursus sit amet. Urna id volutpat lacus laoreet non curabitur gravida arcu. Sed euismod nisi porta lorem. Sit amet aliquam id diam.

    Nisl nisi scelerisque eu ultrices vitae auctor eu augue. Pulvinar etiam non quam lacus suspendisse faucibus interdum posuere. Senectus et netus et malesuada fames ac turpis egestas sed. Purus ut faucibus pulvinar elementum. Scelerisque mauris pellentesque pulvinar pellentesque habitant morbi tristique senectus et. Ullamcorper malesuada proin libero nunc consequat interdum varius sit. Semper quis lectus nulla at volutpat diam ut venenatis. Turpis egestas pretium aenean pharetra magna ac placerat vestibulum. Pellentesque elit eget gravida cum sociis natoque penatibus. Dolor sit amet consectetur adipiscing elit ut aliquam purus sit. Rutrum quisque non tellus orci ac auctor. Vestibulum rhoncus est pellentesque elit ullamcorper dignissim cras tincidunt. Vel pharetra vel turpis nunc eget lorem dolor sed viverra. Non diam phasellus vestibulum lorem sed risus ultricies tristique. Eget mauris pharetra et ultrices neque ornare aenean euismod. Nunc non blandit massa enim nec dui. Ultricies tristique nulla aliquet enim tortor at auctor.

    Mattis aliquam faucibus purus in massa tempor. Nam aliquam sem et tortor consequat id. Tortor at risus viverra adipiscing at in tellus integer feugiat. Egestas tellus rutrum tellus pellentesque eu tincidunt tortor. Habitant morbi tristique senectus et netus et malesuada fames. Vitae ultricies leo integer malesuada nunc vel risus commodo. Netus et malesuada fames ac turpis. Aenean pharetra magna ac placerat vestibulum lectus mauris ultrices eros. Non nisi est sit amet facilisis magna etiam tempor. Volutpat consequat mauris nunc congue.

    Urna et pharetra pharetra massa massa ultricies mi quis hendrerit. Non curabitur gravida arcu ac. Ut lectus arcu bibendum at varius vel pharetra vel. Orci phasellus egestas tellus rutrum tellus pellentesque. Cursus euismod quis viverra nibh cras pulvinar mattis. Risus nullam eget felis eget nunc lobortis. Amet consectetur adipiscing elit pellentesque habitant morbi tristique senectus. Turpis egestas maecenas pharetra convallis posuere morbi. Aliquam purus sit amet luctus venenatis lectus magna fringilla urna. Purus in mollis nunc sed id semper risus in. Augue lacus viverra vitae congue eu. Enim blandit volutpat maecenas volutpat blandit aliquam etiam. Nibh venenatis cras sed felis eget velit. Augue lacus viverra vitae congue eu consequat ac. Sodales ut etiam sit amet nisl purus in mollis. Et netus et malesuada fames. Cras ornare arcu dui vivamus arcu felis. Potenti nullam ac tortor vitae purus faucibus. Sem nulla pharetra diam sit amet nisl suscipit adipiscing bibendum. Sem et tortor consequat id porta nibh venenatis cras.

    Consectetur adipiscing elit duis tristique sollicitudin nibh sit amet. Sed tempus urna et pharetra pharetra massa massa ultricies mi. Sodales ut etiam sit amet nisl purus in mollis. Ornare arcu odio ut sem nulla. Diam maecenas ultricies mi eget mauris pharetra et ultrices neque. Accumsan lacus vel facilisis volutpat. Eleifend donec pretium vulputate sapien nec sagittis aliquam. Aliquet risus feugiat in ante metus. Habitasse platea dictumst quisque sagittis purus sit amet volutpat. Adipiscing at in tellus integer.

    Sit amet cursus sit amet dictum sit amet justo. Libero id faucibus nisl tincidunt eget nullam non. Enim facilisis gravida neque convallis a cras. Tortor at risus viverra adipiscing at in tellus integer feugiat. Fringilla phasellus faucibus scelerisque eleifend. In tellus integer feugiat scelerisque varius morbi enim. Cras semper auctor neque vitae. Pharetra et ultrices neque ornare aenean. Eget magna fermentum iaculis eu. Natoque penatibus et magnis dis. Faucibus purus in massa tempor nec. Non curabitur gravida arcu ac tortor dignissim convallis. Ornare aenean euismod elementum nisi quis eleifend quam adipiscing vitae. Semper auctor neque vitae tempus quam pellentesque. Nunc eget lorem dolor sed viverra. Consectetur a erat nam at lectus urna duis. Tristique risus nec feugiat in fermentum posuere urna nec tincidunt. Augue mauris augue neque gravida in fermentum et sollicitudin. A iaculis at erat pellentesque adipiscing commodo elit at imperdiet. Tincidunt augue interdum velit euismod in pellentesque massa.

    Libero nunc consequat interdum varius. Sit amet est placerat in egestas. Mattis rhoncus urna neque viverra justo nec. Nulla malesuada pellentesque elit eget. Commodo odio aenean sed adipiscing diam. At lectus urna duis convallis. Sed ullamcorper morbi tincidunt ornare. Amet justo donec enim diam vulputate. Sed enim ut sem viverra aliquet eget sit. Ipsum faucibus vitae aliquet nec. Lectus quam id leo in vitae turpis. Ut aliquam purus sit amet luctus venenatis lectus magna. Neque convallis a cras semper auctor neque vitae. Congue nisi vitae suscipit tellus mauris.

    A erat nam at lectus. Massa tincidunt nunc pulvinar sapien et ligula ullamcorper malesuada. Elementum nisi quis eleifend quam adipiscing vitae proin sagittis nisl. Consectetur lorem donec massa sapien faucibus et molestie ac. Dui accumsan sit amet nulla. Vulputate dignissim suspendisse in est. Pellentesque habitant morbi tristique senectus et netus et. Ut tristique et egestas quis ipsum suspendisse ultrices. Convallis tellus id interdum velit laoreet id donec ultrices. At quis risus sed vulputate odio. Non arcu risus quis varius quam quisque. Convallis tellus id interdum velit laoreet id donec ultrices.

    Vulputate ut pharetra sit amet aliquam id. Id diam maecenas ultricies mi eget mauris pharetra et. At erat pellentesque adipiscing commodo elit. Morbi leo urna molestie at elementum eu. Laoreet suspendisse interdum consectetur libero. Facilisis leo vel fringilla est ullamcorper eget. Scelerisque eleifend donec pretium vulputate sapien nec. Ornare lectus sit amet est. Donec adipiscing tristique risus nec feugiat in. Tempus imperdiet nulla malesuada pellentesque elit eget. Malesuada proin libero nunc consequat interdum. Feugiat nibh sed pulvinar proin gravida hendrerit lectus. Vulputate dignissim suspendisse in est ante in nibh mauris. Sed vulputate mi sit amet mauris. Facilisis leo vel fringilla est ullamcorper.</p>
    <Wave />
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

  p {
    @apply text-center antialiased;
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
</style>
