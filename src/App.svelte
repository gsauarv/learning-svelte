<script>
  // array of people
  let peoples = [
    { name: "John", age: 20, id: 1 },
    { name: "Peter", age: 30, id: 2 },
    { name: "Amy", age: 40, id: 3 },
  ];
</script>

<main>
  <!-- looops -->
  {#each peoples as person (person.id)}
    <div>
      <p>{person.name} is {person.age} years old.</p>
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
