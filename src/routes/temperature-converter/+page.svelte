<script lang="ts">
	class Temperature {
		#c = $state(0);
		#f = $state(0);

		get c() {
			return this.#c;
		}

		set c(temperature) {
			this.#c = temperature;
			this.#f = temperature * (9 / 5) + 32;
		}

		get f() {
			return this.#f;
		}

		set f(temperature) {
			this.#f = temperature;
			this.c = (temperature - 32) * (5 / 9);
		}
	}

	const temperature = new Temperature();
</script>

<div class="space-x-5">
	<input type="number" bind:value={temperature.c} />
	<input type="number" bind:value={temperature.f} />
</div>

<style>
	input {
		@apply rounded-lg border border-zinc-200 py-3 px-6;
	}
</style>
