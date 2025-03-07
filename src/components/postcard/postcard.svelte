<script lang="ts">
	export let count: string;
	export let label: string;
	export let imgSrc: string;
	export let bgColor: string;
</script>

<div class="top-contents">
	<div class="texts">
		<strong class="count">{count}</strong>
		<p class="label">{label}</p>
	</div>
	<img class="top-contents-img" src={imgSrc} style="background-color: {bgColor};" />
</div>

<style>
	.texts {
		padding-left: 15px;
	}
	.top-contents {
		height: 100%;
		width: 23.5%;
		display: flex;
		border-radius: 10px;
		background-color: white;
		justify-content: space-between;
		align-items: center;
	}
	.count {
		font-size: xx-large;
	}
	.label {
		font-size: small;
	}
	.top-contents-img {
		width: 50px;
		height: 50px;
		border-radius: 100%;
		margin: 10%;
	}
</style>
