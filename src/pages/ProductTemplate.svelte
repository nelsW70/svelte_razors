<script>
  // STORES
  import products from "../stores/products";
  import globalStore from "../stores/globalStore";
  import { addToCart } from "../stores/cart";
  // COMPONENTS
  import Loading from "../components/Loading.svelte";
  // MODULES
  import { link } from "svelte-routing";
  // VARIABLES
  export let id;
  export let location;
  $: product = $products.find((item) => item.id === parseInt(id));
</script>

<!-- 
<svelte:head>
  <title>{!product ? 'single product' : product.title}</title>
</svelte:head> -->

{#if !product}
  <Loading />
{:else}
  <section class="single-product">
    <!-- back to products -->
    <a href="/products" use:link class="btn btn-primary">back to products</a>
    <!-- single product container -->
    <div class="single-product-container">
      <article class="single-product-image">
        <img src={product.image} alt={product.title} />
      </article>
      <article>
        <h1>{product.title}</h1>
        <h2>${product.price}</h2>
        <p>{product.description}</p>
        <button
          class="btn btn-primary btn-block"
          on:click={() => {
            addToCart(product);
            globalStore.toggleItem('cart', true);
          }}>
          add to cart
        </button>
      </article>
    </div>
  </section>
{/if}
