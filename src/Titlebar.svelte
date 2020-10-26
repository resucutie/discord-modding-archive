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
					navigation: lastBreadCrumb.navigation + split,
				},
			];
			lastBreadCrumb = breadcrumbs[breadcrumbs.length - 1];
		}
	}

	$: updateBreadcrumbs($path);
</script>

<style>
</style>

{#each breadcrumbs as breadcrumb}
	<a
		href={breadcrumb.navigation}
		on:click={() => {
			$path = breadcrumb.navigation;
		}}>{breadcrumb.name}</a>{breadcrumb === breadcrumbs[0] ? ' ' : ' / '}
{/each}
