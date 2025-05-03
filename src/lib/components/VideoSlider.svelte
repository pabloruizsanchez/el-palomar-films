<script>
  import VideoModal from '$lib/components/VideoModal.svelte';
  import { onMount } from 'svelte';

  let videos = [
    { id: 1, localClip: '/videos/clip1.mp4', vimeoId: '940795432', title: 'Pureza - Tío Pepe', thumb: '/thumbs/thumb1.jpg' },
    { id: 2, localClip: '/videos/clip2.mp4', vimeoId: '1074664933', title: 'Nuevas tradiciones - Icónica Sevilla Santalucía Fest', thumb: '/thumbs/thumb2.jpg' },
    { id: 3, localClip: '/videos/clip3.mp4', vimeoId: '257077796', title: 'Alma Bohemia - Tin Fernandez + Inma Salomón', thumb: '/thumbs/thumb3.jpg' },
    { id: 4, localClip: '/videos/clip4.mp4', vimeoId: '465584676', title: 'Sierra de las Nieves - Turismo Costa del Sol', thumb: '/thumbs/thumb4.jpg' },
    { id: 5, localClip: '/videos/clip5.mp4', vimeoId: '660396836', title: 'Liturgia Andaluza - Le Plato', thumb: '/thumbs/thumb5.jpg' },
    { id: 6, localClip: '/videos/clip6.mp4', vimeoId: '239384806', title: 'Real Betis Baloncesto - Energiía Plus', thumb: '/thumbs/thumb6.jpg' },
    { id: 7, localClip: '/videos/clip7.mp4', vimeoId: '1041933180', title: 'El Sol de Andalucia - Tio Pepe', thumb: '/thumbs/thumb7.jpg' },
    { id: 8, localClip: '/videos/clip8.mp4', vimeoId: '1074672574', title: 'Hidden places - Vogana', thumb: '/thumbs/thumb8.jpg' },
    { id: 9, localClip: '/videos/clip9.mp4', vimeoId: '543945718', title: 'Cuevas de Málaga - Turismo Costa del Sol', thumb: '/thumbs/thumb9.jpg' },
    { id: 10, localClip: '/videos/clip10.mp4', vimeoId: '337578620', title: 'The Fog - I am Dive', thumb: '/thumbs/thumb10.jpg' },
    { id: 11, localClip: '/videos/clip11.mp4', vimeoId: '306329031', title: 'Mira Festival', thumb: '/thumbs/thumb11.jpg' },
    { id: 12, localClip: '/videos/clip12.mp4', vimeoId: '374741801', title: 'MTV EMA Sevilla', thumb: '/thumbs/thumb12.jpg' },
    { id: 13, localClip: '/videos/clip13.mp4', vimeoId: '452324511', title: 'Intro Farruquito', thumb: '/thumbs/thumb13.jpg' },
    { id: 14, localClip: '/videos/clip14.mp4', vimeoId: '611849823', title: 'Ioca Group - Future', thumb: '/thumbs/thumb14.jpg' }
  ];

  let duplicatedVideos = [];

  onMount(() => {
    duplicatedVideos = [...videos, ...videos];
  });

  let showModal = false;
  let currentVideo = null;

  const openVideo = (video) => {
    currentVideo = video;
    showModal = true;
  };
</script>

<style>
  @keyframes scroll-left {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }


  .slider {
    display: flex;
    animation: scroll-left 12s linear infinite;
    height: 100%;
    align-items: center;
    gap: 1px;
    background-color: black;
  }

  video {
    transform: translateZ(0);
    image-rendering: auto;
    height: 100%;
    width: auto;
    flex-shrink: 0;
    background-color: black;
  }


  .slider-container {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
    background-color: black;
  }

  .slider {
    display: flex;
    animation: scroll-left 10s linear infinite;
    height: 100%;
    align-items: center;
  }

  video {
    height: 100%;
    width: auto;
    flex-shrink: 0;
    cursor: pointer;
  }

.footer-info {
  background: black;
  color: white;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  font-family: sans-serif;
}

.footer-info .logo {
  height: 32px;
}

.footer-info .contacts {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  text-align: center;
}

.footer-info a {
  color: white;
  text-decoration: none;
}



</style>

<div class="slider-container">
  <div class="slider">
    {#each duplicatedVideos as video (video.id + Math.random())}
      <video
        src={video.localClip}
        muted
        autoplay
        loop
        playsinline
        on:click={() => openVideo(video)}
      ></video>
    {/each}
  </div>
</div>


{#if showModal}
  <VideoModal {currentVideo} bind:showModal {videos} />
{/if}



