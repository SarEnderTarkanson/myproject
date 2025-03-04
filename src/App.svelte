<script>
  import Modal from "./Modal.svelte";

  let showModal = false;

  const toggleModal = () => {
    showModal = !showModal
  }

  let people = [
    { name: "Ender", beltColor: "black", age: 6, id: 1 },
    { name: "Sare", beltColor: "pink", age: 9, id: 2 },
    { name: "Makbule", beltColor: "black", age: 38, id: 3 },
  ];

  const handleClick = (id) => {
    people = people.filter((person) => person.id != id);
  };

  let num = 5;
</script>

<Modal message="Hey there again" {showModal} on:click={toggleModal}/>

<main>
  <button on:click|once={toggleModal}>Open Modal</button>
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      {#if person.beltColor === "black"}
        <p><strong>Master Ninja</strong></p>
      {/if}
      <p>{person.age} years old, {person.beltColor} belt.</p>
      <button on:click={() => handleClick(person.id)}>delete</button>
    </div>
  {:else}
    <p>There are no people to show...</p>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
