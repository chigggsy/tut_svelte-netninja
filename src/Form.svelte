<script>
    import { createEventDispatcher } from "svelte";

    const dispatch = createEventDispatcher();

    let name;
    let beltColour;
    let age;
    let skills = [];

    const handleSubmit = () => {
        const person = {
            name,
            beltColour,
            age,
            skills,
            id: Math.random(),
        };
        dispatch("addPerson", person);
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="Name" bind:value={name} />
    <select bind:value={beltColour}>
        <option value="red">Red</option>
        <option value="yellow">Yellow</option>
        <option value="blue">Blue</option>
        <option value="black">Black</option>
    </select>
    <input type="number" placeholder="Age" bind:value={age} />
    <label for="skills">Skill</label>
    <input type="checkbox" bind:group={skills} value="fighting" /> Fighting
    <br />
    <input type="checkbox" bind:group={skills} value="sneaking" /> Sneaking
    <br />
    <input type="checkbox" bind:group={skills} value="running" /> Running <br />
    <button type="submit">Add</button>
</form>

<style>
    input[type="text"],
    input[type="number"] {
        max-width: 12ch;
    }
</style>
