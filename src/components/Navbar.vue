<template>
	<nav class="navbar navbar-expand-lg navbar-light bg-white shadow-sm">
		<div class="container py-2">
			<a class="navbar-brand" href="/"><span>Dewa</span>property.</a>
			<button
				class="navbar-toggler"
				type="button"
				data-bs-toggle="collapse"
				data-bs-target="#navbarNavAltMarkup"
				aria-controls="navbarNavAltMarkup"
				aria-expanded="false"
				aria-label="Toggle navigation"
			>
				<span class="navbar-toggler-icon"></span>
			</button>
			<div class="collapse navbar-collapse" id="navbarNavAltMarkup">
				<div class="navbar-nav ms-md-auto gap-2">
					<a class="nav-link active" aria-current="page" href="#">Home</a>
					<a class="nav-link" href="#">Property</a>
					<a class="nav-link" href="#">Contact Us</a>
				</div>
			</div>
		</div>
	</nav>
</template>

<script>
export default {
	name: "Navbar",
};
</script>
