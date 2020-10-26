<script>
	export let currentRoute;
	import PageNotFound from "./PageNotFound.svelte";
	import timeline from "./events";

	let selected = timeline[currentRoute.namedParams.id];
</script>

<style>
</style>

{#if selected}
	<svelte:component this={selected.component} />
{:else}
	<PageNotFound />
{/if}
