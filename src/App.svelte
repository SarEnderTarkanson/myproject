<script>
	let people = [
		// { name: "Ender", beltColor: "black", age: 6, id: 1 },
		// { name: "Sare", beltColor: "pink", age: 9, id: 2 },
		// { name: "Makbule", beltColor: "black", age: 38, id: 3 },
	];
</script>

<main>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			<p>{person.age} years old, {person.beltColor} belt.</p>
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
