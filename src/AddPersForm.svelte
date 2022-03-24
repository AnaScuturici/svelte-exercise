<script>
    let name;
    let color;
    let age;
    let skills =[];

    const handleSubmit = () => {
        console.log(name, color, age, skills);
    }

</script>

<h3>Add new person</h3>
<!--preventDefault event modifier-->
<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="color" bind:value={color}>
    <input type="number" placeholder="age" bind:value={age}>
    <label>Skills:</label>
    <input type="checkbox" bind:group={skills} value="fighting">fighting<br>
    <input type="checkbox" bind:group={skills} value="running">running<br>
    <input type="checkbox" bind:group={skills} value="sneaking">sneaking<br>
    <button>Add person</button>
</form>

<style>

</style>