<script>
    import PollStore from "../stores/pollStore.js";
    import PollDetail from "./PollDetail.svelte";

</script>

<div class="poll-list">
    {#each $PollStore as poll(poll.id)} 
    <div>
        <PollDetail poll={poll} on:vote/>
    </div>
    {/each}
</div>

<style>
    .poll-list {
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 20px;
    }
</style>