<script lang="ts">
	let flight = $state<"One-way" | "Return">("One-way")
	let startDate = $state(new Date())
	let endDate = $state(new Date())

	const handleSubmit = (e: SubmitEvent) => {
		e.preventDefault()
		alert(flight + " flight booked for the " + startDate)
	}
</script>

<form onsubmit={(e) => handleSubmit(e)} class="space-x-5">
	<select bind:value={flight}>
		<option value="One-way">One Way</option>
		<option value="Return">Return</option>
	</select>
	<input type="date" bind:value={startDate} />
	<input type="date" bind:value={endDate} disabled={flight == "One-way"} />
	<button type="submit" disabled={flight == "Return" && startDate > endDate}> Confirm </button>
</form>

<style>
	select,
	option,
	input,
	button {
		@apply rounded-lg border border-zinc-200 py-3 px-6 disabled:cursor-not-allowed;
	}
</style>
