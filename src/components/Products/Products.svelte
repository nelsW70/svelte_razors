<script>
  // LIFECYCLES
  import { onMount, onDestroy } from "svelte";
  // STORE
  import products from "../../stores/defaultProducts";
  // VARIABLES
  let localProducts = [];
  onMount(() => {
    products.subscribe((value) => {
      localProducts = value;
    });
  });
</script>

<h1>hello from products component</h1>

{#each localProducts as product}
  <h2>{product.title}</h2>
{/each}
