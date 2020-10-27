<script>
	import { Router } from "svelte-router-spa";
	import Titlebar from "./Titlebar.svelte";
	import Home from "./Home.svelte";
	import Timeline from "./Timeline.svelte";
	import TimelinePoint from "./TimelinePoint.svelte";
	import UserPage from "./UserPage.svelte";
	import UsersPage from "./UsersPage.svelte";
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
		{ name: "users", component: UsersPage },
		{
			name: "users/:id",
			component: UserPage,
		},
		{ name: "404", component: PageNotFound },
	];
</script>

<style>
	main {
		text-align: center;
		padding: 0;
		margin: 0 auto;
	}
	.page {
		padding: 1em;
	}
</style>

<main>
	<Titlebar />
	<div class="page">
		<Router {routes} />
	</div>
</main>
