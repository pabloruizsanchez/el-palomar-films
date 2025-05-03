<script>
  export let video;
  export let onClick;
</script>

<div class="vimeo-thumbnail" on:click={onClick}>
  <img src={`/thumbs/${video.thumb}`} alt={video.title} />
  <div class="title">{video.title}</div>
</div>

<style>
  .vimeo-thumbnail {
    position: relative;
    cursor: pointer;
    display: inline-block;
    margin: 0 10px;
    border-radius: 8px;
    overflow: hidden;
    transition: transform 0.3s ease;
  }

  .vimeo-thumbnail img {
    width: 100%;
    height: auto;
  }

  .vimeo-thumbnail:hover {
    transform: scale(1.05);
  }

  .vimeo-thumbnail .title {
    position: absolute;
    bottom: 10px;
    left: 10px;
    color: white;
    font-size: 16px;
    font-weight: bold;
    background-color: rgba(0, 0, 0, 0.5);
    padding: 5px;
    border-radius: 5px;
  }
</style>
