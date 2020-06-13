<script>
	import EmojiDisplay from './EmojiDisplay.svelte';
	import EmojiDescription from './EmojiDescription.svelte';
	import Button from './Button.svelte';

	let isLoaded = false;
	let currentEmoji = '😊'
	const emojis = ['😊','🚥','🔥','🙏','🐱‍🐉','🐱','🦊','📦','💕'];
	let m = { x: 0, y:0}
	function randomizeEmoji () {
		return emojis[Math.floor(Math.random() * emojis.length)];
	}
	function handleRandomButton() {
		currentEmoji = randomizeEmoji()
	}

	setTimeout( () => {
		isLoaded = true;
	}, 2500)

	function handleMouseMove(event) {
		m.x = event.clientX;
		m.y = event.clientY;
	}
</script>

<div class="container" on:mousemove={handleMouseMove}>
	<p>The mouse position: {m.x} x {m.y}</p>
	<h1>Randomizer Emoji</h1>
	{#each emojis as emoji}
		<li>{emoji}</li>
	{/each}
	{#if isLoaded === true}
	<EmojiDisplay {currentEmoji}/>
	<EmojiDescription/>
	<Button on:click|once={handleRandomButton} title={'🔁 randomizer'}/>
	{:else}
	<h2>Loading...</h2>
	{/if}
	
	<Button title={'Toggle'} on:click={ () => (isLoaded = !isLoaded)}/>
</div>

<svelte:head>
	<link rel="stylesheet" href="/terminal.min.css">
</svelte:head>
<style>
	div{
		margin: 2em;
	}
</style>