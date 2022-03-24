<script>
    export let message = "default value"; //default value will display if no message value is passed as a prop in App
    export let showModal = false;
    export let isPromo = false;
</script>

<!-- forward the click event on to the parent component
register the event without passing any value
invoque the event in the parent component-->

{#if showModal}
<div class="backdrop" class:promo={isPromo} on:click> 
    <div class="modal">
        <p>{message}</p>
    </div>
</div>
{/if}

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        background: rgba(0,0,0, 0.8);
    }
    .modal {
        padding: 10px;
        border-radius: 10px; 
        max-width: 400px;
        margin: 10% auto;
        text-align: center;
        background: white;
    }
    .promo .modal {
        background: crimson;
        color: white;
    }
</style>