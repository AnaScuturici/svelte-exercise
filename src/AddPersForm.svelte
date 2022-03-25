<script>
    // emit a custom event from component to parent, pass data to parent
    import { createEventDispatcher } from "svelte";

    let dispatch = createEventDispatcher();

    let name;
    let color;
    let age;
    let skills =[];

    const handleSubmit = () => {
        const person = {
            name,
            color,
            age,
            skills,
            id: Math.random() //not ideal way to create id...
        };
        dispatch("addPerson", person); //"addPerson" = custom event
    };

</script>

<h3>Add new person</h3>
<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>
    <label for="color">Color</label>
    <select bind:value={color}>
        <option>black</option>
        <option>red</option>
        <option>blue</option>
    </select>
    <label for="skills">Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting">fighting<br>
    <input type="checkbox" bind:group={skills} value="running">running<br>
    <input type="checkbox" bind:group={skills} value="sneaking">sneaking<br>
    <button>Add person</button>
</form>

<style>

</style>