<script lang="ts">
	import { Postcard } from '../../components/postcard/postcard';
	import { Referals } from '../../components/referals/referals';
	import { Product_User } from '../../components/product_user/product_user';
	import Product from '../../components/product.svelte';
	const top_contents = [
		{
			count: '154K',
			label: 'Total Subscribers',
			imgSrc: 'src/image/eye.png',
			bgColor: 'blanchedalmond'
		},
		{
			count: '145',
			label: 'Total Points',
			imgSrc: 'src/image/point.png',
			bgColor: 'rgb(161, 207, 255)'
		},
		{
			count: '15',
			label: 'Total Pages',
			imgSrc: 'src/image/pages.png',
			bgColor: 'rgb(244, 169, 169)'
		},
		{
			count: '2654',
			label: 'Total Paid',
			imgSrc: 'src/image/paid.png',
			bgColor: 'rgb(173, 255, 178)'
		}
	];
	const discussions = [
		{ name: 'lee', imgSrc: 'https://avatars.githubusercontent.com/u/141641630?v=4' },
		{
			name: 'daniel',
			imgSrc:
				'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTofiTkhCGQWTYpkk3-17Hs7xRUd6uXsmqsAQ&s'
		}
	];
	const Users = [
		{
			name: 'leo',
			imgSrc: 'https://img.freepik.com/free-psd/3d-render-avatar-character_23-2150611750.jpg'
		},
		{
			name: 'kim',
			imgSrc:
				'https://img.freepik.com/premium-vector/person-with-blue-shirt-that-says-name-person_1029948-7040.jpg?semt=ais_hybrid'
		}
	];
	const referals = [
		{ domain: 'Facebook', count: '245' },
		{ domain: 'Twitter', count: '235' },
		{ domain: 'Google', count: '210' },
		{ domain: 'Youtube', count: '190' }
	];
</script>

<div class="contents">
	<div class="page-title">
		<strong>Dashboard</strong>
	</div>

	<div class="top-contents-container">
		{#each top_contents as content}
			<Postcard
				count={content.count}
				label={content.label}
				imgSrc={content.imgSrc}
				bgColor={content.bgColor}
			/>
		{/each}
	</div>

	<div class="middle-contents-container">
		<div class="middle-contents-1">
			<Product>
				<div slot="product-name">Users</div>
			</Product>
		</div>

		<div class="middle-contents-2">
			<div style="margin: 20px; font-weight: 700;">Discussion</div>
			{#each discussions as user}
				<Product_User name={user.name} imgSrc={user.imgSrc} />
			{/each}
		</div>
	</div>

	<div class="bottom-contents-container">
		<div class="bottom-contents-1">
			<div style="margin: 20px; font-weight: 700;">Top Referals</div>
			{#each referals as ref}
				<Referals domain={ref.domain} count={ref.count} />
			{/each}
		</div>

		<div class="bottom-contents-2">
			<Product>
				<div slot="product-name">Viewers</div>
			</Product>
		</div>

		<div class="bottom-contents-3">
			<div style="margin: 20px; font-weight: 700;">Users</div>
			{#each Users as user}
				<Product_User name={user.name} imgSrc={user.imgSrc} />
			{/each}
		</div>
	</div>
</div>

<style>
	@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');

	.container {
		display: flex;
		flex-direction: row;
		flex-grow: 1; /* body의 남은 공간을 차지하도록 설정 */
		width: 100%;
		min-width: 100vh; /* 또는 min-height: 100vh; */
	}

	.dash_board {
		width: 100%;
		height: 100%;
		background-color: rgb(246, 246, 246);
	}
	.contents {
		flex-grow: 1;
		height: 100%;
		margin: 2%;
	}
	.top-contents-container {
		display: flex;
		justify-items: space-between;
		height: 14%;
		margin-bottom: 2%;
		gap: 0 2%;
	}
	.page-title {
		display: flex;
		justify-content: left;
		padding-bottom: 1%;
	}
	.middle-contents-container {
		display: flex;
		height: 42%;
		justify-content: space-between;
		gap: 0 2%;
	}
	.middle-contents-1 {
		width: 74.5%;
		height: 100%;
		border-radius: 10px;
		background-color: white;
	}
	.middle-contents-2 {
		width: 23.5%;
		height: 100%;
		border-radius: 10px;
		background-color: white;
	}
	.bottom-contents-container {
		height: 28%;
		display: flex;
		padding-top: 2%;
		justify-content: space-between;
		gap: 0 2%;
	}
	.bottom-contents-1 {
		width: 30%;
		height: 84%;

		border-radius: 10px;
		background-color: white;
	}
	.bottom-contents-2 {
		border-radius: 10px;
		width: 42.5%;
		height: 84%;

		background-color: white;
	}
	.bottom-contents-3 {
		border-radius: 10px;
		width: 23.5%;
		height: 84%;

		background-color: white;
	}
</style>
