<script>
	import { path } from "./stores/path.js";

	let breadcrumbs = [];

	function updateBreadcrumbs() {
		// Reset breadcrumbs.
		breadcrumbs = [
			{
				name: "/",
				navigation: "/",
			},
		];

		// Generate new breadcrumbs.
		let splitPath = $path.split("/").filter((split) => split.length > 0);
		let lastBreadCrumb = breadcrumbs[0];
		for (const split of splitPath) {
			breadcrumbs = [
				...breadcrumbs,
				{
					name: split.replace(/\//g, ""),
					navigation: (
						lastBreadCrumb.navigation +
						"/" +
						split
					).replace(/\/\//g, "/"),
				},
			];
			lastBreadCrumb = breadcrumbs[breadcrumbs.length - 1];
		}
	}

	$: updateBreadcrumbs($path);
</script>

<style>
	.titlebar {
		font-weight: 100;
		font-family: Discord;
		font-size: larger;
		padding: 1em;
		background-color: #292b2f;
		filter: drop-shadow(0px 2px 1px rgba(4, 4, 5, 0.6));
		user-select: none;
	}
</style>

<div class="titlebar">
	{#each breadcrumbs as breadcrumb}
		<a
			href={breadcrumb.navigation}
			on:click={() => {
				$path = breadcrumb.navigation;
			}}>{breadcrumb.name}</a>{breadcrumb === breadcrumbs[0] ? ' ' : ' / '}
	{/each}
</div>
