/* --- VideoSlider.svelte --- */
<script>
  import { onMount } from 'svelte';
  import { videos } from '../VideoList.js';
  import VimeoThumbnail from './VimeoThumbnail.svelte';
  import VideoModal from './VideoModal.svelte';

  let selected = null;
  let scrollRef;

  const handleClick = (video) => {
    selected = video;
  };

  const handleClose = () => {
    selected = null;
  };

  let scrollInterval;

  onMount(() => {
    scrollInterval = setInterval(() => {
      if (scrollRef) scrollRef.scrollLeft += 0.5;
    }, 16);
    return () => clearInterval(scrollInterval);
  });
</script>

<style>
  .slider-container {
    background: black;
    overflow: hidden;
    white-space: nowrap;
    display: flex;
    width: 100vw;
    gap: 10px;
    padding: 10px 0;
  }
</style>

<div bind:this={scrollRef} class="slider-container">
  {#each videos as video}
    <VimeoThumbnail {video} on:click={() => handleClick(video)} />
  {/each}
</div>

{#if selected}
  <VideoModal {selected} on:close={handleClose} />
{/if}


/* --- VimeoThumbnail.svelte --- */
<script>
  export let video;
</script>

<style>
  .thumbnail {
    display: inline-block;
    width: 300px;
    min-width: 300px;
    height: 180px;
    background: black;
    overflow: hidden;
    cursor: pointer;
  }
  video {
    width: 100%;
    height: 100%;
    object-fit: cover