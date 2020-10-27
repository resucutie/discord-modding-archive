<script>
	import User from "./User.svelte";

	export let currentRoute;
</script>

<style>
</style>

<User id={currentRoute.namedParams.id} />
