<script>
	let people = [
		{name: 'Yoshi', beltColour: 'Black', age: 25, id: 1},
		{name: 'Mario', beltColour: 'Orange', age: 45, id: 2},
		{name: 'Luigi', beltColour: 'Brown', age: 35, id: 3}
	]

	const handleDelete = (id) => {
		people = people.filter((person) => person.id != id)
	}
</script>

<main>
	<h1>People</h1>
	{#each people as person (person.id)}
		<div class="person">
			<h4>{person.name}</h4>
			<p>{person.name} is a {person.beltColour} belt and is {person.age} years old. <p>
			<button on:click={() => handleDelete(person.id)}>Delete</button>
		</div>
		{:else} <!-- Empty state-->
		<p>This list here is empty 😭</p>  
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

	.person {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		margin-bottom: 2.5rem;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>