<script lang="ts">
	import { Info } from '../../components/info/info';
	import { Search } from '../../components/search/search';
	import { User } from '../../components/user/user';
	const infoItems = [{ icon: '/image/alarm.png' }, { icon: '/image/flag.png' }];
</script>

<div class="header">
	<Search />
	<div class="info_container">
		<div class="info">
			{#each infoItems as infoItem}
				<Info {infoItem} />
			{/each}
		</div>
		<User />
	</div>
</div>

<style lang="scss">
		.header {
				display: flex;
				flex-direction: row;
				justify-content: space-between;
        .info_container {
            display: flex;
            align-items: center;
            justify-content: right;
            gap: 0 20px;
						.info {
								display: flex;
								align-items: center;
								gap: 0 20px;
						}
        }
		}


</style>
