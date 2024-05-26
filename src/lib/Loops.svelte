<script lang="ts">
  import Modal from "./Modal.svelte";

  let people = [
    { name: "felix", beltColor: "green", age: 34, id: 1 },
    { name: "pepe", beltColor: "gray", age: 22, id: 2 },
    { name: "maria", beltColor: "yellow", age: 20, id: 3 },
  ];

  const handleClick = (id: number) => {
    people = people.filter((person) => person.id !== id);
  };

  let showModal = true;
  const toggleModal = () => (showModal = !showModal);
</script>

<Modal {showModal} on:click={toggleModal}>
  <h3>Add new Person</h3>
  <form>
    <input type="text" placeholder="name" />
    <input type="text" placeholder="belt colour" />
    <button>Add person</button>
  </form>
  <div slot="title">
    <h3>Add new Person!</h3>
  </div>
</Modal>

<button on:click={toggleModal}></button>
<div style="display: flex; column-gap: 30px; ">
  {#each people as persone (persone.id)}
    <div style="display: flex;">
      {persone.name === "felix" ? persone.name : ""}
      <h4 style="color: {persone.beltColor}">{persone.name}</h4>
      <h4 style="padding-left: 10px;">{persone.age}</h4>
    </div>
    <button on:click={() => handleClick(persone.id)}>Delete</button>
  {:else}
    <p>There is not people to show...</p>
  {/each}
</div>
