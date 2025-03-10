<script lang="ts">
	export let title: string = '';
</script>

<div class="root">
	<div class="title">{title}</div>
	<slot />
</div>

<style lang="scss">
	.root {
		width: 100%;
		height: 100%;
		display: flex;
		padding: 1rem;
		background-color: white;
		gap: 1rem;

		.title {
			font-size: 20px;
		}
	}
</style>
