<svelte:head>
	<title>About</title>
</svelte:head>

<script>
	let name = 'world';
	let count = 0;
</script>

<h1>About this site</h1>

<p>This is the 'about' page. There's not much here.</p>

<h1>Hello {name}!</h1>
<input bind:value={name}>

<button on:click={() => count += 1}>
	Clicks: {count}
</button>
