<script lang="ts">
	export let title: string;
	export let className: string = '';
</script>

<div class="basic-container">
	<header class="basic-title">{title}</header>
	<slot />
</div>

<style lang="scss">
	.basic-container {
		width: 100%;
		height: 100%;
		background-color: white;
		border-radius: 10px;
		box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
	}
	.basic-title {
		font-size: 1.2rem;
		font-weight: bold;
		margin-bottom: 10px;
	}
</style>
