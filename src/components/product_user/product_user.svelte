<script lang="ts">
	export let name: string;
	export let imgSrc: string;
</script>

<div class="product-components">
	<div class="user">
		<img class="user-img" style="margin-left: 20px;" src={imgSrc} alt="Error" />
		<p>{name}</p>
	</div>
</div>

<style>
	.product-name {
		font-size: x-large;
		margin: 20px;
	}
	.user {
		display: flex;
		align-items: center;
		gap: 0 10px;
		padding-right: 30px;
	}
	.user-img {
		height: 40px;
		width: 40px;
		border-radius: 80%;
	}
</style>
