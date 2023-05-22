<script lang="ts">
	export let mb: string;
</script>

<div class={`card shadow-sm mb-${mb}`}>
	<div class="card-body">
		<slot />
	</div>
</div>
