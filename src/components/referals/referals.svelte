<script lang="ts">
	export let domain: string;
	export let count: string;
</script>

<div class="sns-list">
	<div class="sns">
		<div>{domain}</div>
		<div>{count}</div>
	</div>
</div>

<style>
	.sns {
		display: flex;
		justify-content: space-between;
		margin: 15px;
	}
</style>
