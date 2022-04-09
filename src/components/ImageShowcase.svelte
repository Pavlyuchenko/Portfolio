<script>
	import ImageLoader from "./ImageLoader.svelte";
	export let imgs;

	let chosenImage = imgs[0];
</script>

<ImageLoader path={chosenImage.path} alt={chosenImage.alt} />
<div class="image-gallery">
	{#each imgs as image}
		<img
			src={image.altPath ? image.altPath : image.path}
			alt={image.alt}
			on:click={() => {
				chosenImage = image;
			}}
			class={image == chosenImage ? "bordered" : "clickable"}
		/>
	{/each}
</div>

<style>
	.image-gallery {
		width: 100%;
		height: 100px;
		display: flex;
		margin-top: 10px;
	}
	img {
		height: 100%;
		margin-right: 10px;
		object-fit: cover;
		width: 100px;
		border-radius: 5px;
	}
	.bordered {
		border: 5px solid #555555;
		box-sizing: border-box;
	}
	.clickable {
		cursor: pointer;
		transition: 0.15s;
		filter: brightness(65%);
	}
	.clickable:hover {
		opacity: 0.7;
	}
</style>
