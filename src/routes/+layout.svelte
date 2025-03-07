<script lang="ts">
	import Header from '../components-route/header/header.svelte';
	import Sidebar from '../components-route/sidebar/sidebar.svelte';
	//import Dashboard from '../components/dashboard/dashboard.svelte';
</script>

<div class="container">
	<Sidebar />
	<div class="dashboard">
		<Header />
		<slot />
		<!--<Dashboard />-->
	</div>
</div>

<style>
	:global(body) {
		background-color: rgb(246, 246, 246);
	}
	.container {
		display: flex;
	}
	.dashboard {
		flex: 1;
		padding: 20px;
	}
</style>
