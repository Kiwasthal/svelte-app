<script>
  import {createEventDispatcher} from 'svelte'
  const dispatch = createEventDispatcher()
  let greet = () => {
    dispatch('greet', 'Hello')
  }
</script>

<button on:click={greet} >Greet</button>