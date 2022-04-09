<script>
	export let points = [
		{ text: "a", image: "https://ik.imagekit.io/velkadomu/vfb_screen_qgDlGQclK.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504351505", content: "asdasd" },
		{ text: "b", image: "https://ik.imagekit.io/velkadomu/vfb_screen_qgDlGQclK.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504351505", content: "asdasd" },
		{ text: "c", image: "https://ik.imagekit.io/velkadomu/vfb_screen_qgDlGQclK.png?ik-sdk-version=javascript-1.4.3&updatedAt=1649504351505", content: "asdasd" },
	];
</script>

<div id="flex">
	{#each points as point}
		<div>
			<img loading="lazy" src={point.image} alt="" />
			<span>{point.text}</span>
			<p>{point.content}</p>
		</div>
	{/each}
</div>

<style>
	#flex {
		display: flex;
		margin-top: 60px;
	}
	#flex div {
		flex: 1;
	}
	#flex span {
		vertical-align: middle;
		margin-left: 10px;
		color: var(--primary);
		font-size: 22px;
		font-weight: 600;
		font-family: "Inter";
	}
	#flex img {
		width: 40px;
		height: 40px;
		vertical-align: middle;
		border-radius: 4px;
	}
	#flex p {
		font-size: 18px;
		color: #6a6a6a;
	}
	@media (max-width: 700px) {
		#flex {
			flex-direction: column;
		}
	}
</style>
