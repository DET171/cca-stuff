<script setup>
import Todo from './components/Todo.vue';
</script>

<template>
	<ul>
		<Todo v-for="todo in todos" :key="todo.id" :todo="todo" />
	</ul>
</template>

<script>
import axios from 'axios';

export default {
	data: () => ({
		todos: [],
	}),
	created() {
		this.fetchTodos();
	},
	methods: {
		async fetchTodos() {
			const todos = (await axios.get('https://jsonplaceholder.typicode.com/todos')).data.slice(0, 15);
			this.todos = todos;
		},
	},
};
</script>

<style lang="less" scoped>
* {
	font-family: sans-serif;
}
</style>