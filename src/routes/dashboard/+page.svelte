<script lang="ts">
	import { Postcard } from '../../components/postcard/postcard';
	import { Basic_User } from '../../components/basic/basic_user/basic_user';
	import { Basic } from '../../components/basic/basic';
	import { Basic_Ref } from '../../components/basic/basic_ref/basic_ref';

	const top_contents = [
		{
			count: '154K',
			label: 'Total Subscribers',
			imgSrc: '/image/eye.png',
			bgColor: 'blanchedalmond'
		},
		{
			count: '145',
			label: 'Total Points',
			imgSrc: '/image/point.png',
			bgColor: 'rgb(161, 207, 255)'
		},
		{
			count: '15',
			label: 'Total Pages',
			imgSrc: '/image/pages.png',
			bgColor: 'rgb(244, 169, 169)'
		},
		{
			count: '2654',
			label: 'Total Paid',
			imgSrc: '/image/paid.png',
			bgColor: 'rgb(173, 255, 178)'
		}
	];
	const users_discusstion = [
		{ name: 'lee', imgSrc: 'https://avatars.githubusercontent.com/u/141641630?v=4' },
		{
			name: 'daniel',
			imgSrc:
				'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTofiTkhCGQWTYpkk3-17Hs7xRUd6uXsmqsAQ&s'
		},
		{ name: 'kim', imgSrc: 'https://avatars.githubusercontent.com/u/141641630?v=4' },
		{
			name: 'cho',
			imgSrc:
				'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTofiTkhCGQWTYpkk3-17Hs7xRUd6uXsmqsAQ&s'
		},
		{ name: 'choi', imgSrc: 'https://avatars.githubusercontent.com/u/141641630?v=4' },
		{
			name: 'leo',
			imgSrc:
				'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTofiTkhCGQWTYpkk3-17Hs7xRUd6uXsmqsAQ&s'
		},
		{ name: 'yang', imgSrc: 'https://avatars.githubusercontent.com/u/141641630?v=4' },
		{
			name: 'ba',
			imgSrc:
				'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTofiTkhCGQWTYpkk3-17Hs7xRUd6uXsmqsAQ&s'
		}
	];
	const users_member = [
		{
			name: 'leo',
			imgSrc: 'https://img.freepik.com/free-psd/3d-render-avatar-character_23-2150611750.jpg'
		},
		{
			name: 'kim',
			imgSrc:
				'https://img.freepik.com/premium-vector/person-with-blue-shirt-that-says-name-person_1029948-7040.jpg?semt=ais_hybrid'
		}
	];
	const referals = [
		{ domain: 'Facebook', count: '245' },
		{ domain: 'Twitter', count: '235' },
		{ domain: 'Google', count: '210' },
		{ domain: 'Youtube', count: '190' }
	];
</script>

<div class="contents">
	<div class="page-title">
		<strong>Dashboard</strong>
	</div>

	<div class="top-contents-container">
		{#each top_contents as content}
			<Postcard
				count={content.count}
				label={content.label}
				imgSrc={content.imgSrc}
				bgColor={content.bgColor}
			/>
		{/each}
	</div>

	<div class="middle-contents-container">
		<div class="Users-Chart">
			<Basic title="Users-Chart" />
		</div>
		<div class="Discussion">
			<Basic title="Discussion">
				<Basic_User users={users_discusstion} />
			</Basic>
		</div>

	</div>

	<div class="bottom-contents-container">
		<div class="Referals">
			<Basic title="Referals">
				<Basic_Ref refs={referals} />
			</Basic>
		</div>

		<div class="Viewers">
			<Basic title="Viewers" />
		</div>

		<div class="Members">
			<Basic title="Members">
				<Basic_User users={users_member} />
			</Basic>
		</div>

	</div>
</div>

<style lang="scss">
	@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');
	@mixin contents-container($height: 42%) {
		display: flex;
		justify-items: space-between;
		height: $height;
		margin-bottom: 2%;
		gap: 0 2%;
	}
	@mixin contents-style($height: 90%, $width: 23.5%) {
		border-radius: 10px;
		height: $height;
		width: $width;
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
	.contents {
		flex-grow: 1;
		height: 100%;
		margin: 2%;
	}
	.page-title {
		display: flex;
		justify-content: left;
		padding-bottom: 1%;
	}
	.top-contents-container {
		@include contents-container($height: 14%);
	}

	.middle-contents-container {
		@include contents-container();
	}

	.bottom-contents-container {
		@include contents-container($height: 28%);
	}
</style>
