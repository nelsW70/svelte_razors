<script>
  // VARIABLES
  export let title = "";
  // LIFECYCLES
  import { onMount, onDestroy } from "svelte";
  // STORE
  import products from "../../stores/defaultProducts";
  // COMPONENTS
  import Product from "./Product.svelte";
  import Loading from "../Loading.svelte";
</script>

<section class="section">
  <h2 class="section-title">{title}</h2>
  <div class="products-center">
    {#each $products as product (product.id)}
      <Product {product} />
    {:else}
      <Loading />
    {/each}
  </div>
</section>
