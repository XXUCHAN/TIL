<script lang="ts">
	import { Postcard } from '../../components/postcard/postcard';
	import { Basic_User } from '../../components/basic/basic_user/basic_user';
	import { Basic } from '../../components/basic/basic';
	import { Basic_Ref } from '../../components/basic/basic_ref/basic_ref';
	import { Input } from '../../components/input/input';
	import { onMount } from 'svelte';
	import { writable } from 'svelte/store';
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
	let addValue = '';
	let editValue = '';
	let editId: number | null;
	let todos = writable<{ id: number; text: string }[]>([]);
	let completedTodos = writable<{ id: number; text: string }[]>([]);

	function dateFormater(id: number) {
		const date = new Date(id);
		return date.toLocaleString();
	}

	onMount(() => {
		const savedTodos = JSON.parse(localStorage.getItem('todos') || '[]');
		const savedCompletedTodos = JSON.parse(localStorage.getItem('completedTodos') || '[]');
		todos.set(savedTodos);
		completedTodos.set(savedCompletedTodos);
	});

	function handler(value: string) {
		const inputValue = { id: Date.now(), text: value.detail };
		const savedTodos = JSON.parse(localStorage.getItem('todos') || '[]');
		savedTodos.push(inputValue);
		localStorage.setItem('todos', JSON.stringify(savedTodos));
		todos.set(savedTodos);
		addValue = '';
		console.log(value.detail);
	}
	/*
	function addTodo(text: string) {
		if (!text.trim()) return;
		const newTodo = { id: Date.now(), text };
		const savedTodos = JSON.parse(localStorage.getItem('todos') || '[]');
		savedTodos.push(newTodo);
		localStorage.setItem('todos', JSON.stringify(savedTodos));
		todos.set(savedTodos);
		addValue = '';
	} */

	function deleteTodo(id: number) {
		const newTodo = JSON.parse(localStorage.getItem('todos') || '[]').filter(
			(todo: { id: number }) => todo.id !== id
		);
		localStorage.setItem('todos', JSON.stringify(newTodo));
		todos.set(newTodo);
	}
	function deleteCompletedTodo(id: number) {
		const newTodo = JSON.parse(localStorage.getItem('completedTodos') || '[]').filter(
			(todo: { id: number }) => todo.id !== id
		);
		localStorage.setItem('completedTodos', JSON.stringify(newTodo));
		completedTodos.set(newTodo);
	}
	function editTodo(id: number) {
		editId = id;
		const todo = JSON.parse(localStorage.getItem('todos') || '[]').find(
			(todo: { id: number }) => todo.id == id
		);
		editValue = todo.text;
	}

	function saveEdit(event: KeyboardEvent) {
		if (event.key === 'Enter') {
			const newTodo = JSON.parse(localStorage.getItem('todos') || '[]').map(
				(todo: { id: number | null }) => (todo.id === editId ? { ...todo, text: editValue } : todo)
			);
			localStorage.setItem('todos', JSON.stringify(newTodo));
			todos.set(newTodo);
			editId = null;
			editValue = '';
		}
	}
	function completedTodo(id: number) {
		const newTodo = JSON.parse(localStorage.getItem('todos') || '[]').find(
			(todo: { id: number }) => todo.id == id
		);
		const savedCompletedTodo = JSON.parse(localStorage.getItem('completedTodos') || '[]');
		savedCompletedTodo.push(newTodo);
		localStorage.setItem('completedTodos', JSON.stringify(savedCompletedTodo));
		completedTodos.set(savedCompletedTodo);
		deleteTodo(id);
	}
</script>

<div class="contents">
	<div class="page-title">
		<strong>Todo List</strong>
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
		<div class="Todo_List">
			<Basic title="Todo List">
				<!-- <input
					type="text"
					bind:value={addValue}
					placeholder="할 일을 입력하세요"
					on:keydown={(evt) => console.log(evt)}
				/> -->
				<div class="todo-input">
					<Input placeholderText="할 일을 입력하세요" on:save={handler} />
				</div>
				<!--
				<button on:click={() => addTodo(addValue)}>추가</button>
				-->
				{#each $todos as todo}
					<li class="todos">
						{#if editId === todo.id}
							<input
								type="text"
								bind:value={editValue}
								placeholder="수정할 내용을 입력하세요"
								on:keydown={saveEdit}
							/>
						{:else}
							{todo.text}
							<button on:click={() => editTodo(todo.id)}>수정</button>
							<button on:click={() => deleteTodo(todo.id)}>삭제</button>
							<button on:click={() => completedTodo(todo.id)}>완료</button>
						{/if}
					</li>
				{/each}
			</Basic>
		</div>

		<div class="Completed_Task">
			<Basic title="Completed Task">
				{#each $completedTodos as todo}
					<li class="completedTodos">
						{todo.text}<span class="datetime">{dateFormater(todo.id)}</span>
						<button on:click={() => deleteCompletedTodo(todo.id)}>삭제</button>
					</li>
				{/each}
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
			<Basic title="Viewers"/>
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
		justify-content: space-between;
		height: $height;
		margin-bottom: 2%;
		gap: 0 2%;
	}
  @mixin contents-style($height: 90%, $width: 23.5%) {
    border-radius: 10px;
    height: $height;
    width: $width;
  }
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
  @mixin todo-style {
    font-size: medium;
    padding: 5px;
  }
  @mixin mid-contents-style {
    flex: 1;
    overflow: scroll;
    border-radius: 10px;
  }
  .contents {
    flex-grow: 1;
    height: 100%;
    margin: 2%;
  }


	.top-contents-container {
		@include contents-container($height: 14%);
	}
  .middle-contents-container {
    @include contents-container($height: 42%);
  }
  .bottom-contents-container {
    @include contents-container($height: 28%);
  }
	.page-title {
		display: flex;
		justify-content: left;
		padding-bottom: 1%;
	}

  .Todo_List {
    @include mid-contents-style();
    .todo-input{
      margin: 10px;
      padding: 5px;
      width: 70%;
    }
    button{
      @include button-style;
    }
    @media (max-width: 880px) {
      input{
        margin: 5px;
        padding: 0px;
        width: 70%;
      }
    }
  }
	.completedTodos {
		text-decoration: line-through;
		.datetime {
			padding-left: 50px;
		}
		@media (max-width: 880px) {
			display: flex;
			margin: 5px;
			text-decoration: line-through;
			.datetime {
				padding-left: 50px;
			}
		}
	}
  .Completed_Task {
    @include mid-contents-style();
    button{
      @include button-style;
    }
  }
	.todos {
		margin: 10px;
		@media (max-width: 880px) {
			margin: 10px;
			display: flex;
		}
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
</style>
