<script>
	import { page } from '$app/stores';
	let currentPage = $page.url.pathname;
</script>

<nav class="navbar navbar-expand-lg navbar-dark bg-dark shadow-sm mb-3">
	<div class="container">
		<a class="navbar-brand" href="/">TODOS</a>
		<button
			class="navbar-toggler"
			type="button"
			data-bs-toggle="collapse"
			data-bs-target="#navMenu"
			aria-controls="navMenu"
			aria-expanded="false"
			aria-label="Toggle navigation">
			<span class="navbar-toggler-icon" />
		</button>
		<div class="collapse navbar-collapse" id="navMenu">
			<ul class="navbar-nav ms-auto">
				<li class="nav-item">
					<!-- prettier-ignore -->
					<a
            class="nav-link"
            class:active={currentPage === '/'} aria-current="page" href="/">
            Home
          </a>
				</li>
			</ul>
		</div>
	</div>
</nav>
