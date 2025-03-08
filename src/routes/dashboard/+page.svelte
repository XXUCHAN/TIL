<script lang="ts">
	import { Postcard } from '../../components/postcard/postcard';
	import { Basic_User } from '../../components/basic/basic_user/basic_user';
	import { Basic } from '../../components/basic/basic';
	import {Basic_Ref} from '../../components/basic/basic_ref/basic_ref';

	const top_contents = [
		{
			count: '154K',
			label: 'Total Subscribers',
			imgSrc: 'src/image/eye.png',
			bgColor: 'blanchedalmond'
		},
		{
			count: '145',
			label: 'Total Points',
			imgSrc: 'src/image/point.png',
			bgColor: 'rgb(161, 207, 255)'
		},
		{
			count: '15',
			label: 'Total Pages',
			imgSrc: 'src/image/pages.png',
			bgColor: 'rgb(244, 169, 169)'
		},
		{
			count: '2654',
			label: 'Total Paid',
			imgSrc: 'src/image/paid.png',
			bgColor: 'rgb(173, 255, 178)'
		}
	];
	const users_discusstion = [
		{ name: 'lee', imgSrc: 'https://avatars.githubusercontent.com/u/141641630?v=4' },
		{
			name: 'daniel',
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
		<div class="middle-contents-1">
			<Basic title="Users-Chart"></Basic>
		</div>

		<div class="middle-contents-2">
			<Basic title="Discusstion">
				<Basic_User users={users_discusstion} />
			</Basic>
		</div>
	</div>

	<div class="bottom-contents-container">
		<div class="bottom-contents-1">
			<Basic title="Referals">
				<Basic_Ref refs={referals} />
			</Basic>
		</div>

		<div class="bottom-contents-2">
			<Basic title="Viewers" />
		</div>

		<div class="bottom-contents-3">
			<Basic title="Members">
				<Basic_User users={users_member} />
			</Basic>
		</div>
	</div>
</div>

<style>
    @import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');
    .contents {
        flex-grow: 1;
        height: 100%;
        margin: 2%;
    }
    .top-contents-container {
        display: flex;
        justify-items: space-between;
        height: 14%;
        margin-bottom: 2%;
        gap: 0 2%;
    }
    .page-title {
        display: flex;
        justify-content: left;
        padding-bottom: 1%;
    }
    .middle-contents-container {
        display: flex;
        height: 42%;
        justify-content: space-between;
        gap: 0 2%;
    }
    .middle-contents-1 {
        width: 74.5%;
        height: 100%;
        border-radius: 10px;
        background-color: white;
    }
    .middle-contents-2 {
        width: 23.5%;
        height: 100%;
        border-radius: 10px;
        background-color: white;
        overflow: scroll;
    }
    .bottom-contents-container {
        height: 28%;
        display: flex;
        padding-top: 2%;
        justify-content: space-between;
        gap: 0 2%;
    }
    .bottom-contents-1 {
        width: 30%;
        height: 84%;
        overflow: scroll;
        border-radius: 10px;
        background-color: white;
    }
    .bottom-contents-2 {
        border-radius: 10px;
        width: 42.5%;
        height: 84%;

        background-color: white;
    }
    .bottom-contents-3 {
        border-radius: 10px;
        width: 23.5%;
        height: 84%;
        overflow: scroll;
        background-color: white;
    }
</style>
