<script>
	import EmojiDisplay from './EmojiDisplay.svelte';
	import EmojiDescription from './EmojiDescription.svelte';

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

<div>
	<h1>Randomizer Emoji</h1>
	{#each emojis as emoji}
		<li>{emoji}</li>
	{/each}
	{#if isLoaded === true}
	<EmojiDisplay {currentEmoji}/>
	<EmojiDescription/>
	<button on:click={handleRandomButton}>🔁 randomizer</button>
	{:else}
	<h2>Loading...</h2>
	{/if}
		
</div>

<style>
	button {
		background-color: #8bd3dd;
		padding: 0.75em;
		border-radius: 0.25em;
		border: 2px solid #000000;
		box-shadow: 0.4rem 0.4rem 0 #222;
	}
	button:hover{
		box-shadow: 0.25rem 0.25rem 0 #222;
		transition: all 0.4s ease 0s;
		background-color: #8bd;
	}
	div{
		margin: 2em;
	}
</style>