<script>
	import { SideMenu } from '../../components/sideMenu/sideMenu';

	const menuItems = [
		{ img: '/image/dashboard.png', text: 'Dashboard' },
		{ img: '/image/payout.png', text: 'Payout' },
		{ img: '/image/inbox.png', text: 'Inbox' },
		{ img: '/image/setting.png', text: 'Settings' },
		{ img: '/image/check.png', text: 'Todo' }
	];
</script>

<div class="sidebar">
	<div class="menu">
		<div class="main-title"><strong>Stamper</strong></div>
		{#each menuItems as item}
			<SideMenu {item} />
		{/each}
	</div>
</div>

<style lang="scss">
	.sidebar {
		width: 12%;
		height: 100vh;
		background-color: white;
		display: flex;
		flex-direction: column;
		align-items: center;
		.menu {
			width: 100%;
			display: flex;
			flex-direction: column;
		}
		.main-title {
			padding: 30px;
			text-align: center;
			color: blue;
			font-weight: bold;
		}
	}
</style>
