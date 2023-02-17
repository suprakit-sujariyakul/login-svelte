<script lang="ts">
	export let userData: object[];
	let username: string,
		password: string,
		userId: number,
		isLoggedIn: boolean = false;

	function handleLogin() {
		for (let user of userData) {
			if (user.username === username && user.address.city === password) {
				userId = user.id - 1;
				isLoggedIn = true;
				return;
			}
		}
		alert('Invalid username or password');
	}

	function handleLogout() {
		isLoggedIn = false;
		username = '';
		password = '';
	}
</script>

{#if isLoggedIn}
	<div class="flex flex-col m-auto items-center p-10  bg-green-100 shadow-2xl rounded-3xl">
		<img
			class="w-24 h-24 mb-5 rounded-full shadow-lg"
			src="https://picsum.photos/id/{userId}/200/200"
			alt="{userData[userId].name}'s picture"
		/>
		<div class="mb-2 text-lg">Name: {userData[userId].name}</div>
		<div class="mb-2 text-lg">Email: {userData[userId].email}</div>
		<div class="text-lg">Phone: {userData[userId].phone}</div>
		<button
			type="button"
			on:click={handleLogout}
			class="text-white bg-red-200 hover:bg-red-300 focus:ring-4 focus:outline-none focus:ring-red-100  text-xl rounded-lg p-2.5 mt-5 text-center"
			>Log out</button
		>
	</div>
{:else}
	<form
		on:submit={handleLogin}
		class="flex flex-col m-auto text-center p-10  bg-green-100 shadow-2xl rounded-3xl"
	>
		<label for="username" class="mb-2 text-xl">Username</label>
		<input
			type="text"
			id="username"
			class="border border-gray-300 text-gray-900  rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 mb-5"
			bind:value={username}
			required
		/>
		<label for="password" class="mb-2 text-xl">Password</label>
		<input
			type="password"
			id="password"
			class="border border-gray-300 text-gray-900 rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 mb-5"
			bind:value={password}
			required
		/>
		<button
			type="submit"
			class="text-white bg-red-200 hover:bg-red-300 focus:ring-4 focus:outline-none focus:ring-red-100  text-xl rounded-lg py-2.5 mt-2 text-center"
			>Login</button
		>
	</form>
{/if}
