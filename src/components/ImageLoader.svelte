<script>
	export let path;
	export let alt;
	export let description;

	import IntersectionObserver from "./IntersectionObserver.svelte";
	import Image from "./Image.svelte";
	let nativeLoading = false;
</script>

<!-- Does it work? -->
<IntersectionObserver once={true} let:intersecting>
	{#if intersecting || nativeLoading}
		<Image {alt} {path} {description} />
	{/if}
</IntersectionObserver>
