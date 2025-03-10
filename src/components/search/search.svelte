<script lang="ts">
	import Input from '../input/input.svelte';
	function handler(value: string) {
		const searchValue = { id: Date.now(), text: value.detail };
		localStorage.setItem('search', JSON.stringify(searchValue));
		console.log(value.detail);
	}
</script>

<div class="search-container">
	<div class="search">
		<img
			class="img"
			src="https://img.icons8.com/?size=100&id=59878&format=png&color=000000"
			alt="Error"
		/>
		<Input placeholderText="search" on:save={handler} />
	</div>
</div>

<style lang="scss">
	.search-container {
		width: 50%;
		gap: 0 10px;
		.search {
			display: flex;
			align-items: center;
			justify-content: left;
			margin-left: 20px;
			margin-top: 20px;
			height: 40px;
			border-radius: 40px;
			background-color: rgb(220, 214, 248);
			.img {
				padding: 15px;
				width: 20px;
				height: 20px;
			}
		}
	}
</style>
