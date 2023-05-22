<script>
	import '../app.scss';
	import Navbar from '@/components/Navbar.svelte';
</script>

<Navbar />
<main class="container">
	<slot />
</main>

<style>
	@import url('https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.5/font/bootstrap-icons.css');
</style>
