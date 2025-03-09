<script lang="ts">
	export let title: string;
</script>

<div class="basic-container">
	<header class="basic-title">{title}</header>
	<slot></slot>  <!-- 부모가 넣은 콘텐츠가 들어감 -->
</div>

<style lang="scss">
		.basic-container {
				margin: 20px;
				font-weight: 700;
				font-size: x-large;
				.basic-title {
						color: black;
				}
		}
</style>