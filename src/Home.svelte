<script>
	import { navigateTo } from "svelte-router-spa";
	import { path } from "./stores/path";
</script>

<style>
</style>

<h1>All The Discord Modding Drama</h1>
<a
	href="/events"
	on:click={() => {
		$path = '/events';
	}}>Timeline</a>
