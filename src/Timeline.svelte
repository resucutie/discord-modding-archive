<script>
	import { path } from "./stores/path";
	import timeline from "./events";
</script>

<style>
</style>

<h1>Timeline</h1>
{#each Object.keys(timeline).sort((a, b) => {
	if (a.time > b.time) return 1;
	if (a.time < b.time) return -1;
	return 0;
}) as time}
	<a
		href={`/events/${time}`}
		on:click={() => {
			$path = `/events/${time}`;
		}}>{timeline[time].name}</a><br />
{/each}
