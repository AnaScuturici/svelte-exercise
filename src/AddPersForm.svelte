<script>
    let name;
    let color;
    let age;
    let fighting = false;
    let running = false;
    let sneaking = false;

    const handleSubmit = () => {
        console.log(name, color, age, fighting, running, sneaking);
    }

</script>

<h3>Add new person</h3>
<!--preventDefault event modifier-->
<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="color" bind:value={color}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:checked={fighting}>fighting<br>
    <input type="checkbox" bind:checked={running}>running<br>
    <input type="checkbox" bind:checked={sneaking}>sneaking<br>
    <button>Add person</button>
</form>

<style>

</style>