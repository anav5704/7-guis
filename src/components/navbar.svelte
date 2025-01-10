<script lang="ts">
	import { getStores } from "$app/stores"
	const { page } = getStores()

	const links = [
		{
			label: "Home",
			href: "/"
		},
		{
			label: "Counter",
			href: "/counter"
		},
		{
			label: "Temperature Converter",
			href: "/temperature-converter"
		},
		{
			label: "Flight Booking",
			href: "/flight-booking"
		}
	]
</script>

<nav>
	{#each links as { label, href }}
		<a {href} class={`${$page.url.pathname == href && "text-orange-600"}`}>{label}</a>
	{/each}
</nav>

<style>
	nav {
		@apply flex flex-col w-80 border-r border-zinc-200;

		a {
			@apply p-5 border-b border-zinc-200;
		}
	}
</style>
