<script>
	import users from "./users";
	import User from "./User.svelte";

	console.log(users);
</script>

<style>
</style>

{#each Object.keys(users).sort() as user}
	<User id={(console.log(user), user)} /><br />
{/each}
