<script lang="ts">
	export let title: string;
	export let className: string = '';
</script>

<div class={`basic-container ${className}`}>
	<header class="basic-title">{title}</header>
	<slot />
</div>

<style lang="scss">
	@mixin button-style {
		cursor: pointer;
		padding: 5px 10px;
		border: none;
		background-color: #0056b3;
		color: white;
		border-radius: 5px;
		&:hover {
			background-color: #0056b3;
		}
		@media (max-width: 880px) {
			cursor: pointer;
			font-size: small;
			padding: 1px 2px;
			border: none;
			background-color: #0056b3;
			color: white;
			border-radius: 5px;
			&:hover {
				background-color: #0056b3;
			}
		}
	}

	@mixin contents-style($height: 90%, $width: 23.5%) {
		border-radius: 10px;
		height: $height;
		width: $width;
	}
	@mixin todo-style {
		font-size: medium;
		padding: 5px;
	}
	@mixin mid-contents-style {
		flex: 1;
		overflow: scroll;
		border-radius: 10px;
	}

	.basic-container {
		width: 50%;
		height: auto;
		padding: 20px;
		background-color: white;
		border-radius: 10px;
		box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
	}
	.Users-Chart {
		@include contents-style($width: 80%);
	}
	.Discussion {
		@include contents-style();
	}
	.Referals {
		@include contents-style($height: 60%, $width: 30%);
	}
	.Viewers {
		@include contents-style($height: 60%, $width: 42.5%);
	}
	.Members {
		@include contents-style($height: 60%);
	}

	.Todo_List {
		@include mid-contents-style();
		:global(input) {
			margin: 10px;
			padding: 5px;
			width: 70%;
		}
		:global(button) {
			@include button-style;
		}
		@media (max-width: 880px) {
			:global(input) {
				margin: 5px;
				padding: 0px;
				width: 70%;
			}
		}
	}

	.Completed_Task {
		@include mid-contents-style();

		:global(button) {
			@include button-style;
		}
	}
	.basic-title {
		font-size: 1.2rem;
		font-weight: bold;
		margin-bottom: 10px;
	}
</style>
