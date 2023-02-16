<form class="flex flex-col m-auto text-center p-10  bg-green-100 shadow-2xl rounded-3xl">
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
		type="text"
		id="password"
		class="border border-gray-300 text-gray-900 rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 mb-5"
		bind:value={password}
		required
	/>
	<button
		type="submit"
		class="text-white bg-red-200 hover:bg-red-300 focus:ring-4 focus:outline-none focus:ring-red-100  text-xl rounded-lg py-2.5 mt-2 text-center"
		on:click={onLogin}>Login</button
	>
</form>
