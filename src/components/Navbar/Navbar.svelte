<script>
  // COMPONENTS
  import SmallNavbar from "./SmallNavbar.svelte";
  import BigNavbar from "./BigNavbar.svelte";
  // GLOBAL STORE
  import globalStore from "../../stores/globalStore";
  // VARIABLES
  let screenWidth;
  $: if (screenWidth > 992) {
    globalStore.toggleItem("sidebar", false);
  }
</script>

<svelte:window bind:innerWidth={screenWidth} />

{#if screenWidth > 992}
  <BigNavbar />
{:else}
  <SmallNavbar />
{/if}
