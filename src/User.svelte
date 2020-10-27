<script>
	import users from "./users";
	import { path } from "./stores/path";
	export let id;
	export let size;

	!size ? (size = "inline") : 0;

	let user = users[id];
</script>

<style>
	.user {
		display: inline-flex;
		align-items: center;
		transform: translateY(3px);
	}
	img {
		height: 1em;
		width: auto;
		border-radius: 100%;
		padding-right: 2px;
	}
</style>

{#if user}
	{#if size === 'inline'}
		<a
			class="user"
			href={`/users/${id}`}
			on:click={() => {
				$path = `/users/${id}`;
			}}><img
				src={user.profilePictures?.length > 0 ? user.profilePictures[0] : '/favicon.png'} />{user.name}</a>
	{:else}
		<div>{user.name}</div>
	{/if}
{:else}Unknown User{/if}
