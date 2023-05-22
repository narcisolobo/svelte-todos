<script lang="ts">
	import type { ITodo } from '@/types/types';
	import TodoItem from './TodoItem.svelte';
	import Card from './Card.svelte';
	export let todos: ITodo[];
</script>

{#each todos as todo (todo.id)}
	<TodoItem {todo} on:deleteTodo />
{:else}
	<Card mb="2">
		<p class="card-text">No todos to display.</p>
	</Card>
{/each}
