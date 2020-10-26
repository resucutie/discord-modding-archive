<script>
	import users from "./users";
	export let id;
	export let size;

	!size ? (size = "inline") : 0;

	let user = users[id];
	console.log(
		user.profilePictures?.length > 0
			? "https://cors-anywhere.herokuapp.com/" + user.profilePictures[0]
			: "./favicon.png"
	);
</script>

<style>
	img {
		height: 1em;
		width: auto;
		border-radius: 100%;
	}
</style>

{#if user}
	{#if size === 'inline'}
		<span><img
				src={user.profilePictures?.length > 0 ? user.profilePictures[0] : '../favicon.png'} />{user.name}</span>
	{:else}
		<div>{user.name}</div>
	{/if}
{:else}Unknown User{/if}
