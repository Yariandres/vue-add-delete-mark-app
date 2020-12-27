<template>
	<div>
		<li class="listItem">
			<p v-bind:class="{ 'isComplete': todo.completed }">
				{{ todo.name }}
			</p>

			<span>
				<input type="checkbox" v-on:change="markComplete" />

				<button class="btnDelete" @click="$emit('delete-todo', todo.id )">
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
		border: 1px solid rgb(221, 222, 223);
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
		border: none;
		padding: 10px;
		font-weight: bold;
		color: #fff;
		cursor: pointer;
	}
	.isComplete {
		text-decoration: line-through;
		color: rgb(194, 194, 194);
	}
</style>
