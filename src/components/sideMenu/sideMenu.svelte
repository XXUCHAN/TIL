<script>
	export let item;
</script>

<a href={`/${item.text.toLowerCase()}`} class="menu-item">
	<img class="img" src={item.img} alt="Error" />
	<p class="text">{item.text}</p>
</a>

<style lang="scss">
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
      .img {
          height: 20px;
          width: 20px;
      }
			.text {
				margin-left: 10px;
			}
			&:hover {
				background: rgb(198, 213, 245);
				color: blue;
			}
	}






</style>
