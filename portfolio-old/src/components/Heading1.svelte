<script>
	export let description = "";
	export let heading = "";
	export let id = "";
</script>

<div {id}>
	<span>{description}</span>
	<hr />
	<h3>{heading}</h3>
</div>

<style>
	div {
		margin-top: 60px;
	}
	span {
		color: #6a6a6a;
		font-family: "Inter";
		font-size: 14px;
		font-weight: 400;
	}
	h3 {
		font-family: "Inter";
		font-weight: 500;
		font-size: 30px;
		position: relative;

		color: var(--primary);
		margin-top: 6px;
	}
	h3:after {
		position: absolute;
		content: "";
		height: 3px;
		bottom: -8px;

		left: 0;
		width: 30px;
		background: var(--secondary);
	}
	hr {
		border: 0;
		border-top: 1px solid #c4c4c4;
		margin-bottom: 20px;
	}
</style>
