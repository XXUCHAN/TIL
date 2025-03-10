<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let text: string = '';
	export let icon: string | undefined = undefined;
	export let size: 'sm' | 'md' | 'lg' = 'lg';

	export let disabled: boolean = false;
	export let ghost: boolean = false;

	// export let onClick: (evt: MouseEvent) => void;
	const dispatch = createEventDispatcher<{ custom: MouseEvent }>();
</script>

<div class="root" data-size={size} on:click={(evt) => dispatch('custom', evt)}>
	<slot name="let-icon" />
	<div class="text">{text}</div>
	<slot name="right-icon" />
</div>

<style lang="scss">
	.root {
	}
</style>
