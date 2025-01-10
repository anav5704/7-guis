<script lang="ts">
	import Navbar from "../components/navbar.svelte"
	import "../app.css"

	let { children } = $props()
</script>

<main class="flex">
	<Navbar />
	<div class="grid place-content-center h-screen w-screen">
		{@render children()}
	</div>
</main>
