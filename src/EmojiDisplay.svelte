<script>
  export let emoji;
	let currentEmoji = emoji;
	setTimeout(() => {
		currentEmoji = '😢'
	}, 1000);
</script>

<style>
  div{
    font-size: 3em;
    margin-bottom: 0.5em;
  }
</style>

<div>{currentEmoji}</div>
