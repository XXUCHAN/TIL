<script lang="ts">
	export let refs: {domain: string; count: string }[];
</script>

<div class="sns-list">
	{#each refs as ref (ref.domain)}
		<div class="sns">
			<p>{ref.domain}</p>
			<p>{ref.count}</p>
		</div>
	{/each}
</div>

<style>
    .sns {
        display: flex;
        justify-content: space-between;
				font-size: medium;
				overflow: scroll;
    }
</style>
