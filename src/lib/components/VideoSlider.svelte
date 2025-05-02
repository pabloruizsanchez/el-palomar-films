<script>
	import { onMount } from 'svelte';
	import VimeoPlayer from './VimeoPlayer.svelte';

	let showModal = false;
	let currentVimeoUrl = '';

	const videos = [
		{ src: '/videos/clip1.mp4', vimeo: 'https://player.vimeo.com/video/940795432' },
		{ src: '/videos/clip2.mp4', vimeo: 'https://player.vimeo.com/video/1074664933' },
		{ src: '/videos/clip3.mp4', vimeo: 'https://player.vimeo.com/video/257077796' },
		{ src: '/videos/clip4.mp4', vimeo: 'https://player.vimeo.com/video/465584676' },
		{ src: '/videos/clip5.mp4', vimeo: 'https://player.vimeo.com/video/660396836' },
		{ src: '/videos/clip6.mp4', vimeo: 'https://player.vimeo.com/video/239384806' },
		{ src: '/videos/clip7.mp4', vimeo: 'https://player.vimeo.com/video/1041933180' },
		{ src: '/videos/clip8.mp4', vimeo: 'https://player.vimeo.com/video/1074672574' },
		{ src: '/videos/clip9.mp4', vimeo: 'https://player.vimeo.com/video/543945718' },
		{ src: '/videos/clip10.mp4', vimeo: 'https://player.vimeo.com/video/337578620' },
		{ src: '/videos/clip11.mp4', vimeo: 'https://player.vimeo.com/video/306329031' }
	];

	const openModal = (vimeoUrl) => {
		currentVimeoUrl = vimeoUrl;
		showModal = true;
	};

	const closeModal = () => {
		showModal = false;
	};
</script>

<style>
	.slider-track {
		display: flex;
		width: max-content;
		animation: scroll-left 60s linear infinite;
	}
	@keyframes scroll-left {
		from {
			transform: translateX(0%);
		}
		to {
			transform: translateX(-50%);
		}
	}
	video::-webkit-media-controls {
		display: none !important;
	}
</style>

<div class="relative w-screen h-screen overflow-hidden bg-black">
	<div class="slider-track">
		{#each [...videos, ...videos] as video (video.src + Math.random())}
			<video
				src={video.src}
				on:click={() => openModal(video.vimeo)}
				class="mx-2"
				style="height: 90vh;"
				autoplay
				muted
				loop
				playsinline
			></video>
		{/each}
	</div>

	{#if showModal}
		<div class="fixed inset-0 bg-black bg-opacity-90 flex items-center justify-center z-50">
			<div class="relative w-[80vw] h-[45vw] max-w-[1280px]">
				<button class="absolute top-2 right-2 text-white text-2xl" on:click={closeModal}>×</button>
				<VimeoPlayer {currentVimeoUrl} />
			</div>
		</div>
	{/if}
</div>
