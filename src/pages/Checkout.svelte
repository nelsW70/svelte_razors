<script>
  // MODULES
  import { onMount } from "svelte";
  import { navigate, link } from "svelte-routing";
  // STORES
  import user from "../stores/user";
  import { cartTotal } from "../stores/cart";
  // LIFECYCLES
  onMount(() => {
    if (!$user.jwt) {
      navigate("/");
    }
  });
  // FUNCTIONS
  function handleSubmit() {
    console.log("form submitted");
  }
  // VARIABLES
  let name = "";
  $: isEmpty = !name;
</script>

{#if $cartTotal > 0}
  <section class="form">
    <h2 class="section-title">checkout</h2>
    <form class="checkout-form" on:submit|preventDefault={handleSubmit}>
      <h3>order total : ${$cartTotal}</h3>
      <!-- single input -->
      <div class="form-control">
        <label for="name">your name</label>
        <input type="text" id="name" bind:value={name} />
      </div>
      <!-- end of single input -->
      <!-- stripe stuff -->
      <!-- end of stripe stuff -->
      <!-- error message -->
      {#if isEmpty}
        <p class="form-empty">please fill out name field</p>
      {/if}
      <!-- submit button -->
      <button
        class="btn btn-block btn-primary"
        type="submit"
        disabled={isEmpty}
        class:disabled={isEmpty}>submit</button>
    </form>
  </section>
{:else}
  <div class="checkout-empty">
    <h2>your cart is empty</h2>
    <a href="/products" use:link class="btn btn-primary"> fill it </a>
  </div>
{/if}
