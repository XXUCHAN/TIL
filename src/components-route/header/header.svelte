<script lang="ts">
	import { Info } from '../../components/info/info';
	import { Search } from '../../components/search/search';
	import { User } from '../../components/user/user';
	const infoItems = [{ icon: 'src/image/alarm.png' }, { icon: 'src/image/flag.png' }];
</script>

<div class="header">
	<Search />
	<div class="header-right">
		<div class="info">
			{#each infoItems as infoItem}
				<Info {infoItem} />
			{/each}
		</div>
		<User />
	</div>
</div>

<style>
	.header {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	.header-right {
		display: flex;
		align-items: center;
		justify-content: right;
		gap: 0 20px;
	}
	.info {
		display: flex;
		align-items: center;
		justify-content: right;
		gap: 0 20px;
	}
</style>
