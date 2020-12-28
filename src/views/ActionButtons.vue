<template>
	<div class="actionButtons">
		<button @click="$emit('remove-all-todos')" class="removeAllTodos">
			Remove All
		</button>

		<button @click="$emit('mark-all-completed')" class="markAllCompleted">
			Mark All Done
		</button>
	</div>
</template>

<style scoped>
	.actionButtons {
		text-align: center;
		margin-bottom: 40px;
	}
	.removeAllTodos {
		background-color: rgb(255, 238, 0);
		border: 4px solid rgb(7, 6, 31);
		border-radius: 10px;
		padding: 10px;
		font-weight: bolder;
		color: rgb(12, 12, 51);
		cursor: pointer;
	}
    
	.markAllCompleted {
		background-color: rgb(255, 166, 0);
		border: 4px solid rgb(7, 6, 31);
		border-radius: 10px;
		padding: 10px;
		font-weight: bolder;
		color: rgb(12, 12, 51);
		cursor: pointer;
	}
</style>
