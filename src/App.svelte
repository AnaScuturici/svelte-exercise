<script>
	let people = [
		{name: "a", color: "red", age: 25, id: 1},
		{name: "b", color: "black", age: 22, id: 2},
		{name: "c", color: "blue", age: 20, id: 3}
	];

</script>

<main>
	{#each people as person (person.id)}
	<div>
		<h4>{person.name}</h4>
		<p>{person.age} years old, {person.color} belt</p>
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