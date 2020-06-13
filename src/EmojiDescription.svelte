<script>
  let description = '';
  $: characters = description.length;
  $: words = description.split(' ').length;
</script>

<style>
  div{
    margin: 1em 0;
  }
</style>

<!-- markup (zero or more items) goes here -->
<div>
  <p>{description}</p>
  <textarea bind:value={description} rows="7"/>
  <p>Characters count: {characters}</p>
  <p>Words count: {words}</p>
</div>