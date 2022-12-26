<script lang="ts">
	import Navbar from "../components/Navbar.svelte";
	export let status: number;
	export let error: Error;

	const dev = process.env.NODE_ENV === "development";
</script>

<svelte:head>
	<title>{status} - Chevy</title>
</svelte:head>

<header>
	<Navbar />
</header>

<div class="d-flex align-items-center justify-content-center vh-100">
	<div class="container">
		<div>
			<h1>{status}</h1>
			<div>
				<p class="fs-3">{error.message}</p>
			</div>
			<div>
				<a href="./" class="btn btn-primary btn-lg"
					><i class="bi bi-house" />
					Home</a
				><a
					href="https://github.com/Chevyself/portfolio"
					class="btn btn-secondary btn-lg"
					><i class="bi bi-pencil-square" /> Report Issue</a
				>
			</div>
		</div>
	</div>
</div>

{#if dev && error.stack}
	<pre>{error.stack}</pre>
{/if}

<style>
</style>
