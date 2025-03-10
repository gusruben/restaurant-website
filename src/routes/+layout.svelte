<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

{@render children()}

<svelte:head>
	<title>Azur</title>
</svelte:head>