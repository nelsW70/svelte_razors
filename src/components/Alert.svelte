<script>
  // ANIMATIONS
  import { fly, fade } from "svelte/transition";
  // STORES
  import globalStore from "../stores/globalStore";
  // MODULES
  import { onMount, onDestroy } from "svelte";
  // FUNCTIONS
  const handleClose = () => {
    globalStore.toggleItem("alert", false);
  };
  // VARIABLES
  let timeout;
  // LIFECYCLES
  onMount(() => {
    timeout = setTimeout(() => {
      globalStore.toggleItem("alert", false);
    }, 3000);
  });
  onDestroy(() => {
    clearTimeout(timeout);
  });
</script>

<div
  class="alert-container"
  in:fly={{ y: -200, duration: 1000 }}
  out:fade={{ duration: 0 }}
  class:alert-danger={$globalStore.alertDanger}>
  <div class="alert">
    <p>{$globalStore.alertText}</p>
    <button class="alert-close" on:click={handleClose}>
      <i class="fas fa-window-close" />
    </button>
  </div>
</div>
