<script>
	import EmojiDisplay from './EmojiDisplay.svelte';
	import EmojiDescription from './EmojiDescription.svelte';
	import Button from './Button.svelte';

	let isLoaded = false;
	let currentEmoji = '😊'
	const emojis = ['😊','🚥','🔥','🙏','🐱‍🐉','🐱','🦊','📦','💕'];
	function randomizeEmoji () {
		return emojis[Math.floor(Math.random() * emojis.length)];
	}
	function handleRandomButton() {
		currentEmoji = randomizeEmoji()
	}

	setTimeout( () => {
		isLoaded = true;
	}, 2500)
</script>

<div class="container">
	<h1>Randomizer Emoji</h1>
	{#each emojis as emoji}
		<li>{emoji}</li>
	{/each}
	{#if isLoaded === true}
	<EmojiDisplay {currentEmoji}/>
	<EmojiDescription/>
	<Button on:click={handleRandomButton} title={'🔁 randomizer'}/>
	{:else}
	<h2>Loading...</h2>
	{/if}
		
</div>

<svelte:head>
	<link rel="stylesheet" href="/terminal.min.css">
</svelte:head>
<style>
	div{
		margin: 2em;
	}
</style>