<script>
  // LIFECYCLES
  import { onMount, onDestroy } from "svelte";
  // STORE
  import products from "../../stores/defaultProducts";
  // COMPONENTS
  import Product from "./Product.svelte";
  // VARIABLES
  export let title = "";
</script>

<section class="section">
  <h2 class="section-title">{title}</h2>
  <div class="products-center">
    {#each $products as product (product.id)}
      <Product {product} />
    {/each}
  </div>
</section>
