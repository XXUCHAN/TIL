<script>
	export let item;
</script>

<a href={`/${item.text.toLowerCase()}`} class="menu-item">
	<img class="menu-img" src={item.img} alt="Error" />
	<p class="menu-text">{item.text}</p>
</a>

<style>
	.menu-item {
		text-decoration: none;
		display: flex;
		align-items: center;
		background-color: white;
		border: none;
		cursor: pointer;
		color: rgb(145, 144, 144);
		width: 100%;
		height: 40px;
		border-radius: 5px;
		transition: 0.3s;
		font-size: medium;
	}

	.menu-item:hover {
		background: rgb(198, 213, 245);
		color: blue;
	}

	.menu-text {
		margin-left: 10px;
	}

	.menu-img {
		height: 20px;
		width: 20px;
	}
</style>
