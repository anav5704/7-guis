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
			label: "Temp Converter",
			href: "/temp-converter"
		},
		{
			label: "Flight Booking",
			href: "/flight-booking"
		},
		{
			label: "Timer",
			href: "/timer"
		}
	]
</script>

<aside>
	{#each links as { label, href }}
		<a {href} class={`${$page.url.pathname == href && "text-orange-600"}`}>{label}</a>
	{/each}
</aside>

<style>
	aside {
		@apply flex flex-col w-80 border-r border-zinc-200;

		a {
			@apply p-5 border-b border-zinc-200;
		}
	}
</style>
