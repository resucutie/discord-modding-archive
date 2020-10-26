<script>
	import { navigateTo } from "svelte-router-spa";
	import { path } from "./stores/path";
</script>

<style>
</style>

<h1>Discord Modding Archive</h1>
<a
	href="/events"
	on:click={() => {
		$path = '/events';
	}}>Timeline</a>

<a href="https://pull.git.ci/process/KyzaGitHub/discord-modding-archive">Trigger
	Website Update</a>
