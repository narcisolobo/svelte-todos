<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import type { ITodo } from '@/types/types';
	import Card from './Card.svelte';

	const dispatch = createEventDispatcher<{ deleteTodo: { todoId: string } }>();
	export let todo: ITodo;
	function handleClickDelete() {
		dispatch('deleteTodo', { todoId: todo.id });
	}
</script>

<Card mb="2">
	<div class="d-flex justify-content-between align-items-center">
		<div class="form-check">
			<input
				class="form-check-input"
				type="checkbox"
				value=""
				id={todo.id}
				bind:checked={todo.isComplete} />
			<!-- prettier-ignore -->
			<label
				class="form-check-label"
				class:text-decoration-line-through={todo.isComplete}
				for={todo.id}>
				{todo.task}
			</label>
		</div>
		<button class="btn btn-sm btn-danger" on:click={handleClickDelete}>
			<i class="bi bi-trash-fill" />
		</button>
	</div>
</Card>
