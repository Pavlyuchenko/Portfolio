<script>
	export let path;
	export let alt;
	export let width = 100;
	export let description = "";

	let modal_div;
	let modalImage;

	function modal() {
		modal_div.style.display = "block";
		let imgWidth = modalImage.width;
		let imgHeight = modalImage.height;
		let innerWidth = window.innerWidth;
		let innerHeight = window.innerHeight;

		console.log(imgWidth);
		console.log(imgHeight);
		/* if (imgWidth / imgHeight + 0.2 < innerWidth / innerHeight) {
			modalImage.style.maxHeight = "90%";
			console.log("hey");
		} else {
			modalImage.style.maxWidth = "95%";
			modalImage.style.maxHeight = "90%";
		} */
	}
	function hideImage() {
		modal_div.style.display = "none";
	}
</script>

<figure>
	<img
		src={path}
		{alt}
		class="image"
		style="width: {width}%;"
		on:click={() => {
			modal();
		}}
	/>
	{#if description != ""}
		<figcaption><i>{description}</i></figcaption>
	{/if}
</figure>

<div class="modal" bind:this={modal_div} on:click={hideImage}>
	<img src={path} {alt} bind:this={modalImage} />
</div>

<style>
	figure {
		margin: 0;
	}
	figcaption {
		font-size: 16px;
		text-align: center;
		margin-top: 5px;
		margin-bottom: 40px;
		color: #6a6a6a;
	}
	.image {
		margin-top: 40px;
		margin-left: 50%;
		transform: translateX(-50%);
		border-radius: 12px;
		max-height: calc(100% - 100px);

		cursor: zoom-in;
		transition: 0.15s;
	}
	.image:hover {
		opacity: 0.85;
	}

	.modal {
		display: none; /* Hidden by default */
		position: fixed; /* Stay in place */
		z-index: 1; /* Sit on top */
		padding-top: 50px; /* Location of the box */
		left: 0;
		top: 0;
		width: 100%; /* Full width */
		height: 100%; /* Full height */
		background-color: rgb(0, 0, 0); /* Fallback color */
		background-color: rgba(0, 0, 0, 0.9); /* Black w/ opacity */
	}
	.modal img {
		margin: auto;
		display: block;
		border-radius: 12px;
		animation: show 0.15s ease-in-out;
		cursor: zoom-out;

		max-height: 90%;
		max-width: 90%;
	}
	@keyframes show {
		0% {
			transform: scale(0.7);
		}
		100% {
			transform: scale(1);
		}
	}
</style>
