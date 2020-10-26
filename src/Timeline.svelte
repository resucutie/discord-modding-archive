<script>
	import { path } from "./stores/path";
	import timeline from "./events";
</script>

<style>
</style>

<h1>Timeline</h1>
{#each Object.keys(timeline) as time}
	<a
		href={`/events/${time}`}
		on:click={() => {
			$path = `/events/${time}`;
		}}>{timeline[time].name}</a><br />
{/each}
