<script>
  import { count } from '../store/stores';
  let decrement = () => {
    count.update(value => value - 1);
  };
</script>

<button on:click={decrement}>Decrement</button>
