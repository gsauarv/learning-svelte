<script>
  // import statements should be inside script tags
  import Modal from "./components/Model.svelte";
  // array of people
  let peoples = [
    { name: "John", age: 20, id: 1 },
    { name: "Peter", age: 30, id: 2 },
    { name: "Amy", age: 40, id: 3 },
  ];

  const handleClick = (id) => {
    peoples = peoples.filter((person) => person.id != id);
  };

  let num = 2;
</script>

<!-- imported modal from components -->

<Modal />
<main>
  <!-- looops -->
  {#each peoples as person (person.id)}
    <div>
      <p>{person.name} is {person.age} years old.</p>
      {#if person.age > 20}
        <p>You {person.name} need work on yourself</p>
      {:else}
        <p>You are awesome</p>
      {/if}
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

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
