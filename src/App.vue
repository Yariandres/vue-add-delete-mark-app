<template>
	<div>
		<div class="heading">
			<h1>Todo list</h1>
		</div>

		<addTodo v-on:add-todo="addTodo"></addTodo>
		<Todos v-bind:todos="todos" v-on:delete-todo="deleteTodoItem"></Todos>
	</div>
</template>

<script>
	import Todos from './views/Todos';
	import addTodo from './views/AddTodo';

	export default {
		name: 'app',
		components: {
			Todos,
			addTodo,
		},
		data() {
			return {
				todos: [
					{
						id: Math.floor(Math.random() * Math.floor(10000)),
						name: 'Make dinner',
						completed: false,
					},
					{
						id: Math.floor(Math.random() * Math.floor(10000)),
						name: 'Clean the house',
						completed: false,
					},
					{
						id: Math.floor(Math.random() * Math.floor(10000)),
						name: 'Buy groceries',
						completed: false,
					},
				],
			};
		},
		methods: {
			deleteTodoItem(id) {
				this.todos = this.todos.filter(todo => todo.id !== id);

      },
      addTodo(newTodo) {
        this.todos = [...this.todos, newTodo]
      }
		},
	};
</script>

<style>
	* {
		box-sizing: border-box;
	}
	html {
		font-family: sans-serif;
	}
	body {
		margin: 0;
	}

	.heading {
		text-align: center;
		color: #fff;
		background-color: #f88b6a;
		padding: 10px;
	}
	h1 {
		letter-spacing: 2px;
		text-transform: uppercase;
	}
</style>
