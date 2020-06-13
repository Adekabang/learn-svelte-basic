<script>
	import EmojiDisplay from './EmojiDisplay.svelte';
</script>

<div>
	<h1>Randomizer Emoji</h1>
	<EmojiDisplay emoji={'😊'}/>
	<EmojiDisplay emoji={'🦊'}/>
	<EmojiDisplay emoji={'🐱'}/>
	<button>🔁 randomizer</button>
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