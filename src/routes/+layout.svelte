<script lang="ts">
	import Sidebar from "../components/sidebar.svelte"
	import "../app.css"

	let { children } = $props()
</script>

<main class="flex">
	<Sidebar />
	<div class="grid place-content-center h-screen w-screen">
		{@render children()}
	</div>
</main>
