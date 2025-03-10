<script lang="ts">
	export let refs: { domain: string; count: string }[];
</script>

<div class="sns-list">
	{#each refs as ref (ref.domain)}
		<li class="sns">
			<p>{ref.domain}</p>
			<p>{ref.count}</p>
		</li>
	{/each}
</div>

<style lang="scss">
	.sns-list {
		height: 70%;
		overflow: scroll;
		.sns {
			display: flex;
			justify-content: space-between;
			font-size: medium;
		}
	}
</style>
