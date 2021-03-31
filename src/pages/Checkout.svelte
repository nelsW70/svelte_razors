<script>
  // MODULES
  import { onMount } from "svelte";
  import { navigate, link } from "svelte-routing";
  // STORES
  import user from "../stores/user";
  import { cartTotal } from "../stores/cart";
  // LIFECYCLES
  onMount(() => {
    if (!user.jwt) {
      navigate("/");
    }
  });
</script>

<h1>welcome to checkout page</h1>
<h1>welcome to checkout page</h1>
<h1>welcome to checkout page</h1>
<h1>welcome to checkout page</h1>
<h1>welcome to checkout page</h1>
