<script lang="ts">
	import Login from '../lib/Login.svelte';
	import { onMount } from 'svelte';

	let data: object[] = [],
		picture: object[] = [];

	onMount(async function fetchUserData() {
		const res = await fetch('https://jsonplaceholder.typicode.com/users');
		data = await res.json();
	});
</script>

<Login userData={data} />
