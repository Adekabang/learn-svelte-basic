<script>
import { onMount, onDestroy, beforeUpdate, afterUpdate } from 'svelte'
  let description = '';
  $: characters = description.length;
  $: words = description.split(' ').length;
  function handleSubmit(event) {
    event.preventDefault();
    console.log('form submitted, thanks!');
    description = ''
  }

  onMount(function () {
    console.log('onMount')
  })
  onDestroy(function () {
    console.log('onDestroy')
  })
  beforeUpdate(function () {
    console.log('beforeUpdate')
  })
  afterUpdate(function () {
    console.log('afterUpdate')
  })
</script>

<style>
  div{
    margin: 1em 0;
  }
</style>

<!-- markup (zero or more items) goes here -->
<div class="form-group">
  <p>{description}</p>
  <form on:submit|preventDefault={handleSubmit}>
    <textarea bind:value={description} rows="7"/>
    <button type="submit">Save</button>
  </form>
  <p>Characters count: {characters}</p>
  <p>Words count: {words}</p>
</div>