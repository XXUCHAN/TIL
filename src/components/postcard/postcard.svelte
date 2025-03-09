<script lang="ts">
	export let count: string;
	export let label: string;
	export let imgSrc: string;
	export let bgColor: string;
</script>

<div class="postcard">
	<div class="text">
		<strong class="count">{count}</strong>
		<p class="label">{label}</p>
	</div>
	<img class="img" src={imgSrc} style="background-color: {bgColor};" alt="Error"/>
</div>

<style lang="scss">

	.postcard {
			height: 100%;
			width: 23.5%;
			display: flex;
			border-radius: 10px;
			background-color: white;
			justify-content: space-between;
			align-items: center;
      .text {
          padding-left: 15px;
          .count {
              font-size: xx-large;
          }
          .label {
              font-size: small;
          }
      }
      .img {
          width: 50px;
          height: 50px;
          border-radius: 100%;
          margin: 10%;
      }
	}



</style>
