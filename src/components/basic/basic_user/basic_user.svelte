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

<style>
    .user-list {
        width: 23.5%;
        height: 100%;
        border-radius: 10px;
        background-color: white;
    }
    .user {
        display: flex;
        align-items: center;
        gap: 0 10px;
        padding-right: 30px;
				font-size: medium;
    }
    .user-img {
        height: 30px;
        width: 30px;
        border-radius: 80%;
    }
</style>