<script lang="ts">
	let count = $state(0)
</script>

<svelte:head>
	<title>Counter</title>
</svelte:head>

<div class="space-x-5">
	<button onclick={() => count--}>-</button>
	<input type="number" disabled bind:value={count} />
	<button onclick={() => count++}>+</button>
</div>

<style>
	input,
	button {
		@apply rounded-lg border border-zinc-200 py-3 px-6;
	}
</style>
