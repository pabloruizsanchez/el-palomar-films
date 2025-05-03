<script>
  export let currentVideo;
  export let showModal;
  export let videos = [];

  const closeModal = () => showModal = false;

  const getIndex = () => videos.findIndex(v => v.id === currentVideo.id);

  const next = () => {
    const index = getIndex();
    currentVideo = videos[(index + 1) % videos.length];
  };

  const prev = () => {
    const index = getIndex();
    currentVideo = videos[(index - 1 + videos.length) % videos.length];
  };
</script>

<style>
  .modal {
    position: fixed;
    inset: 0;
    background-color: black;
    z-index: 1000;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 0;
    margin: 0;
  }

  iframe.video-frame {
    width: 100vw;
    height: calc(100vh - 100px);
    border: none;
    background-color: black;
    display: block;
    margin: 0;
    padding: 0;
    position: relative;
  }

  .controls {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 100%;
    display: flex;
    justify-content: space-between;
    pointer-events: none;
    padding: 0 1rem;
    box-sizing: border-box;
    z-index: 10;
  }

  .button {
    background: rgba(0, 0, 0, 0.5);
    color: white;
    font-size: 2rem;
    padding: 1rem;
    pointer-events: all;
    cursor: pointer;
    border: none;
  }

  .thumbs {
  position: relative;
  display: flex;
  gap: 0.5rem;
  overflow-x: auto;
  overflow-y: hidden;
  width: 100%;
  padding: 0.5rem 1rem;
  justify-content: flex-start;
  box-sizing: border-box;
  background-color: black;
  z-index: 20;
  scroll-behavior: smooth;
}

  .thumbs img {
    height: 60px;
    cursor: pointer;
    opacity: 0.5;
    transition: opacity 0.2s ease;
  }

  .thumbs img.active {
    opacity: 1;
    border: 2px solid white;
  }
</style>

{#if showModal}
  <div class="modal" on:click|self={closeModal}>
    <iframe
      class="video-frame"
      src={`https://player.vimeo.com/video/${currentVideo.vimeoId}?autoplay=1&muted=0`}
      allow="autoplay; fullscreen"
      allowfullscreen
    ></iframe>

    

    <div class="thumbs">
      {#each videos as video}
        <img
          src={`https://vumbnail.com/${video.vimeoId}.jpg`}
          alt={video.title}
          class:active={video.id === currentVideo.id}
          on:click={() => currentVideo = video}
        />
      {/each}
    </div>
  </div>
{/if}
