<script>
    let name;
    let color;
    let age;
</script>

<h3>Add new person</h3>
<form>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="text" placeholder="color" bind:value={color}>
    <input type="number" placeholder="age" bind:value={age}>
    <button>Add person</button>
</form>

<style>

</style>