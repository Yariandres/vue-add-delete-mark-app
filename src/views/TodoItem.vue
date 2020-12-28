<template>
	<div>
		<li class="listItem">
			<input type="checkbox" v-on:change="markComplete" />
			<p v-bind:class="{ 'isComplete': todo.completed }">
				{{ todo.name }}
			</p>

			<span>
				<button
					class="btnDelete"
					@click="$emit('delete-todo', todo.id)"
				>
					Delete
				</button>
			</span>
		</li>
	</div>
</template>

<script>
	export default {
		props: ['todo'],

		methods: {
			markComplete() {
				this.todo.completed = !this.todo.completed;
			},
		},
	};
</script>

<style scoped>
	.listItem {
		list-style: none;
		font-weight: bold;
		padding: 20px 20px;

		background-color: #75f1e1;
		border: 4px solid rgb(7, 6, 31);
		border-radius: 10px;
		margin: 10px 0;

		display: flex;
		align-items: baseline;
	}

	span {
		margin-left: auto;
	}

	.btnDelete {
		background-color: orangered;
		border: 4px solid rgb(7, 6, 31);
		border-radius: 10px;
		padding: 10px;
		font-weight: bold;
		color: #fff;
		cursor: pointer;
	}
	p {
		margin-left: 10px;
	}
	.isComplete {
		text-decoration: line-through;
		color: rgb(194, 194, 194);
	}
</style>
