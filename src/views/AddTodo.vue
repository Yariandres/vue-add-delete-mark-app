<template>
	<div class="formGroup">
		<form @submit="addTodo">
			<input
				type="text"
				placeholder="Add a todo..."
				v-model="title"
				required
			/>

			<button class="inputBtn" @click="addTodo">Add</button>
		</form>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				title: '',
			};
		},

		methods: {
			addTodo(e) {
				e.preventDefault();
				const newTodo = {
					id: Math.floor(Math.random() * Math.floor(10000)),
					name: this.title,
					completed: false,
				};

				this.$emit('add-todo', newTodo);
				this.title = '';
			},
		},
	};
</script>

<style scoped>
	.formGroup {
		text-align: center;
		padding: 30px 0;
	}

	form {
		width: 100%;
	}

	input[type='text'],
	select {
		padding: 10px;
		border: 4px solid rgb(7, 6, 31);
		border-radius: 10px;
		width: 40%;
		margin-right: 10px;
	}

	.inputBtn {
		background-color: greenyellow;
		border: 4px solid rgb(7, 6, 31);
		border-radius: 10px;
		padding: 10px;
		font-weight: bold;
		color: inherit;
		cursor: pointer;
	}
</style>
