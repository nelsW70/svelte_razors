<script>
  // ANIMATIONS
  import { fly, fade } from "svelte/transition";
  // STORES
  import globalStore from "../stores/globalStore";
  // LIFECYCLES
  import { onMount, onDestroy } from "svelte";
  // FUNCTIONS
  const handleClose = () => {
    console.log("alert closed");
  };
</script>

<div
  class="alert-container"
  in:fly={{ y: -200, duration: 1000 }}
  out:fade={{ duration: 0 }}>
  <div class="alert">
    <p>some dummy text</p>
    <button class="alert-close" on:click={handleClose}>
      <i class="fas fa-window-close" />
    </button>
  </div>
</div>
