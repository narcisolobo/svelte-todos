<script lang="ts">
	import type { ITodo } from '@/types/types';
	import TodoForm from './TodoForm.svelte';
	import TodoList from './TodoList.svelte';

	let todos: ITodo[] = [];

	function handleAddTodo(e: CustomEvent<{ todo: ITodo }>) {
		todos = todos.concat(e.detail.todo);
	}

	function handleDeleteTodo(e: CustomEvent<{ todoId: string }>) {
		todos = todos.filter((todo) => todo.id !== e.detail.todoId);
	}
</script>

<TodoForm on:addTodo={handleAddTodo} />
<TodoList {todos} on:deleteTodo={handleDeleteTodo} />
