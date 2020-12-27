<template>
	<div class="formGroup">
		<form @submit="addTodo">
			<input
				type="text"
				placeholder="Add a todo..."
				v-model="title"
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
                }

				this.$emit('add-todo', newTodo)
				this.title = '';
			},
        }
        
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
		border: 1px solid #ccc;
		width: 40%;
		margin-right: 10px;
	}

	.inputBtn {
		background-color: greenyellow;
		border: none;
		padding: 10px;
		font-weight: bold;
		color: inherit;
		cursor: pointer;
	}
</style>
