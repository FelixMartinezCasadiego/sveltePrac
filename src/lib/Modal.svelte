<script>
  // export let message = "";
  export let showModal = true;
  let isPromo = true;
</script>

{#if showModal}
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <div class="backdrop" class:promo={isPromo} on:click>
    <div class="modal">
      <!-- <p>{message}</p> -->
      <slot></slot>
      <slot name="title"></slot>
    </div>
  </div>
{/if}

<style></style>
