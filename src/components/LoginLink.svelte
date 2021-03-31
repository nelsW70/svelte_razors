<script>
  // STORES
  import user from "../stores/user";
  import globalStore from "../stores/globalStore";
  // MODULES
  import { link } from "svelte-routing";
  // logout functionality
  import { logoutUser } from "../stores/user";
</script>

{#if $user.jwt}
  <a
    href="/"
    class="logout-btn"
    on:click={() => {
      logoutUser();
      globalStore.toggleItem('sidebar', false);
    }}>logout</a>
{:else}
  <a
    href="/login"
    on:click={() => {
      globalStore.toggleItem('sidebar', false);
    }}>login</a>
{/if}
