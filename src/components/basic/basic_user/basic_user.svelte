<script lang="ts">
	export let users: { name: string; imgSrc: string }[];
</script>

<div class="user-list">
	{#each users as user (user.name)}
		<div class="user">
			<img class="user-img" src={user.imgSrc} alt="User Image" />
			<p>{user.name}</p>
		</div>
	{/each}
</div>

<style lang="scss">
	.user-list {
		width: 100%;
		height: 80%;
		overflow: scroll;
		border-radius: 10px;
		background-color: white;
		.user {
			display: flex;
			align-items: center;
			gap: 5px;
			padding-right: 30px;
			font-size: medium;
			.user-img {
				height: 30px;
				width: 30px;
				border-radius: 50%;
			}
		}
	}
</style>
