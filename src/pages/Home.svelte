<script>
  // MODULES
  import { link } from "svelte-routing";
  // COMPONENTS
  import Hero from "../components/Hero.svelte";
  // featured products
  import Featured from "../components/Products/Featured.svelte";
</script>

<Hero>
  <a href="/products" class="btn btn-primary btn-hero" use:link>shop now</a>
</Hero>
<Featured title="featured products" />
