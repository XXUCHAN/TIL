<script lang="ts">
	import Header from '../components-route/header/header.svelte';
	import Sidebar from '../components-route/sidebar/sidebar.svelte';
</script>

<div class="container">
	<Sidebar />
	<div class="dashboard">
		<Header />
		<slot />
	</div>
</div>

<style>
	.container {
		display: flex;
	}
	.dashboard {
		flex: 1;
		padding: 20px;
	}
</style>
