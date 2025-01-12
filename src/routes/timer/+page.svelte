<script lang="ts">
	let elapsed = $state(0)
	let duration = $state(0)
	let interval: number

	const start = () => {
		interval = setInterval(() => {
			elapsed += 0.1

			if (elapsed > duration) {
				elapsed = duration
				clearInterval(interval)
			}
		}, 100)
	}

	const reset = () => {
		duration = 0
		elapsed = 0
		start()
	}

	$effect(() => {
		if (!duration) return
		start()

		return () => clearInterval(interval)
	})
</script>

<svelte:head>
	<title>Timer</title>
</svelte:head>

<div class="gap-5 flex flex-col">
	<progress max={duration} value={elapsed}></progress>
	<input type="range" bind:value={duration} min="1" max="10" step="1" />
	<button onclick={reset}>Reset</button>
</div>

<style>
	butto {
		@apply rounded-lg border border-zinc-200 py-3 px-6 disabled:cursor-not-allowed;
	}
</style>
