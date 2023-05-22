<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import type { ITodo } from '@/types/types';
	import Card from './Card.svelte';

	let dispatch = createEventDispatcher<{ addTodo: { todo: ITodo } }>();

	let todo: ITodo = {
		id: crypto.randomUUID(),
		task: '',
		isComplete: false
	};

	const handleSubmit = () => {
		dispatch('addTodo', { todo });
		todo = {
			id: crypto.randomUUID(),
			task: '',
			isComplete: false
		};
	};
</script>

<Card mb="3">
	<form on:submit|preventDefault={handleSubmit}>
		<div class="form-floating mb-3">
			<input
				class="form-control"
				type="text"
				name="task"
				id="task"
				bind:value={todo.task}
				placeholder="Add new todo" />
			<label for="task">Add new todo</label>
		</div>
		<div class="text-end">
			<button class="btn btn-primary" type="submit">Add Todo</button>
		</div>
	</form>
</Card>
