<script lang="ts">
	let name: string;
	name = 'Suchan Lee';
</script>

<div class="user">
	<img class="img" src="https://avatars.githubusercontent.com/u/141641630?v=4" alt="Error" />
	<p>{name}</p>
</div>

<style lang="scss">
	.user {
			display: flex;
			align-items: center;
			gap: 0 10px;
			padding-right: 30px;
      .img {
          height: 40px;
          width: 40px;
          border-radius: 80%;
      }
	}

</style>
