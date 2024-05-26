<script lang="ts">
  let name = "";
  let beltColour = "";
  let age = 0;

  /* let fighting = false;
  let sneaking = false;
  let running = false; */

  let skills: string[] = [];

  const handleSubmit = () => console.log(name, beltColour, age, skills);
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="name" bind:value={name} />
  <input type="text" placeholder="belt colour" bind:value={beltColour} />
  <input type="number" placeholder="age" bind:value={age} />

  <!-- svelte-ignore a11y-label-has-associated-control -->
  <label>Skills:</label>
  <!-- <input type="checkbox" bind:checked={fighting} /> Fighting <br />
  <input type="checkbox" bind:checked={sneaking} /> Sneaking <br />
  <input type="checkbox" bind:checked={running} /> Running <br /> -->

  <input type="checkbox" bind:group={skills} value="add1" /> Fighting <br />
  <input type="checkbox" bind:group={skills} value="sneaking" /> Sneaking
  <br />
  <input type="checkbox" bind:group={skills} value="running" /> Running <br />

  <button>Add person</button>
</form>

<style></style>
