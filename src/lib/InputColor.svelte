<script lang="ts">
  /* import type { FormEventHandler } from "svelte/elements"; */

  let beltColor = "black";

  const handleCick = () => {
    beltColor = "orange";
  };

  /* const handleInput: FormEventHandler<HTMLInputElement> = (e) => {
    beltColor = (e.target as HTMLInputElement).value;
  }; */
</script>

<div>
  <p style="color:{beltColor}">{beltColor} belt color</p>
  <button on:click={handleCick}> reset belt color </button>
  <!-- <input type="text" on:input={handleInput} value={beltColor}/> -->

  <input type="text" bind:value={beltColor} />
</div>
