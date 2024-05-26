<script lang="ts">
  let firstName = "Jhon";
  let lastName = "Snow";

  $: fullName = `${firstName} ${lastName}`;
</script>

<div>
  <p>{fullName}</p>

  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
</div>
