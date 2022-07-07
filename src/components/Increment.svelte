<script>
  import { count } from '../store/stores';
  let increment = () => {
    count.update(value => value + 1);
  };
</script>

<button on:click={increment}>Increment</button>
