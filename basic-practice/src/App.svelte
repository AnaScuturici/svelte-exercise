<script>
	import Modal from "./Modal.svelte";
	import AddPersForm from "./AddPersForm.svelte";

	let showModal = false;

	const toggleModal = () => {
		showModal = !showModal;
	}

	let people = [
		{name: "A", color: "red", age: 25, id: 1},
		{name: "B", color: "black", age: 22, id: 2},
		{name: "C", color: "blue", age: 20, id: 3}
	];

	const handleClick = (id) => {
		people = people.filter(person => person.id !== id);
	};

	const addPerson = (e) => {
		//console.log(e.detail);
		const person = e.detail;
		people = [person, ...people];
		showModal = false;
	};

</script>

<Modal showModal={showModal} on:click={toggleModal}>
	<AddPersForm on:addPerson={addPerson}/>
</Modal>
<main>
	<button on:click|once={toggleModal}>Open Modal</button>
	{#each people as person (person.id)}
	<div>
		<h4>{person.name}</h4>
		{#if person.color === "black"}
		<p><strong>master ninja</strong></p>
		 {/if}
		<p>{person.age} years old, {person.color} belt</p>
		{#if person.skills}
		<p>Skills: {person.skills}</p>
		{/if}
		<button on:click={() => handleClick(person.id)}>Delete</button>
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