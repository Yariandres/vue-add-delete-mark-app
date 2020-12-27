<template>
	<div>		

		<div class="todolist">
			<ul
				class="listGroup"
				v-for="(todo, index) in todos"
				v-bind:key="index"
			>
				<todo-item
					v-bind:todo="todo"
					v-on:delete-todo="$emit('delete-todo', todo.id)"
				></todo-item>
			</ul>
		</div>
	</div>
</template>

<script>
	import TodoItem from './TodoItem';

	export default {
		components: { TodoItem },
		props: ['todos']		
	};
</script>

<style scoped>
	.listGroup {
		padding: 10px 20px;
		margin: auto;
		background-color: #fff679;
		width: 50%;
		height: 100%;
	}
</style>
