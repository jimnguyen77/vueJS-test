<template>
	<div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
		<h3>
			{{ task.text }}
			<!-- long way -->
			<!--div @click="onDelete(task.id)" class="delete">&times;</div-->
			<!-- short way -->
			<div @click="$emit('delete-task', task.id)" class="delete">&times;</div>
		</h3>
		<p>{{ task.day }}</p>
	</div>
</template>

<script>
export default {
	name: 'Task',
	props: {
		task: Object
	},
	// long way (using @click=onDelete)
	/*methods: {
		onDelete(id) {
			this.$emit('delete-task', id)
		}
	}*/
}
</script>

<style>
.task {
	background: #f4f4f4;
	margin: 5px;
	padding: 10px 20px;
	cursor: pointer;
}

.task.reminder {
	border-left: 5px solid green;
}

.task h3 {
	display: flex;
	align-items: center;
	justify-content: space-between;
}

.task .delete {
	color: red;
	font-size:1.25em;
	font-weight:900;
}
</style>