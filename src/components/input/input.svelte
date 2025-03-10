<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	let addValue: string = '';
	export let placeholderText: string = '';
	const dispatch = createEventDispatcher();
	function save(e) {
		dispatch('save', e);
	}
</script>

<input
	type="text"
	placeholder={placeholderText}
	on:keydown={(event) => {
		console.log(event);
		if (event.key === 'Enter') {
			save(event.target.value);
			//console.log(event.target.value);

		}
	}}
/>

<style lang="scss">
	input {
		width: 100%;
		height: 100%;
		background-color: white;
		border: none;
		font-size: 14px;
	}
</style>
