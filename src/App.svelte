<script>
	import { Router } from "svelte-router-spa";
	import Titlebar from "./Titlebar.svelte";
	import Home from "./Home.svelte";
	import Timeline from "./Timeline.svelte";
	import TimelinePoint from "./TimelinePoint.svelte";
	import PageNotFound from "./PageNotFound.svelte";

	const routes = [
		{
			name: "/",
			component: Home,
		},
		{ name: "events", component: Timeline },
		{
			name: "events/:id",
			component: TimelinePoint,
		},
		{ name: "404", component: PageNotFound },
	];
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}
</style>

<main>
	<Titlebar />
	<Router {routes} />
</main>
