<script>
    import { createEventDispatcher } from "svelte";

    let dispatch = createEventDispatcher();

    let name;
    let beltColor;
    let age;
    let skills = [];
    const handleSubmit = () => {
        const person = {
            name,
            beltColor,
            age,
            skills,
            id: Math.random(),
        };
        dispatch('addPerson', person)
    };
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name} />
    <input type="number" placeholder="age" bind:value={age} />
    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value="figthing" />Fighting<br />
    <input type="checkbox" bind:group={skills} value="sneaking" />Sneaking<br />
    <input type="checkbox" bind:group={skills} value="running" />Running<br />
    <label>Belt Color</label>
    <select bind:value={beltColor}>
        <option value="Black">Black</option>
        <option value="Orange">Orange</option>
        <option value="Brown">Brown</option>
        <option value="White">White</option>
    </select>
    <br />
    <button>Add Person</button>
</form>

<style>
</style>
