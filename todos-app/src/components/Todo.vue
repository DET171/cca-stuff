<script setup>
const props = defineProps({
	todo: Object,
});
</script>

<template>
	<h1 :class="{ done: todo.completed, todo }">{{ todo.id }}: {{ todo.title }}</h1>
</template>

<script>
export default {
	name: 'Todo',
};
</script>

<style lang="less" scoped>
.undone {
	background-color: crimson;
	color: white;
	border: 5px solid rgb(153, 3, 33);
}
.todo {
	padding: 30px;
	margin: 20px auto;
	width: 50%;
	.undone();
}
.done {
	background-color: chartreuse;
	border: 5px solid rgb(87, 173, 0);
}
</style>