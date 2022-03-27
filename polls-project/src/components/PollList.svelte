<script>
    import { onDestroy, onMount } from "svelte"; 
    import PollStore from "../stores/pollStore.js";
    import PollDetail from "./PollDetail.svelte";

    export let polls = [];

    PollStore.subscribe((data) => {
        polls = data;
    });

    onMount(() => {
        // ex: getting data from a db
        console.log("component mounted");
    });
    onDestroy(() => {
        // unsub from store
        console.log("component destroyed");
    })
</script>

<div class="poll-list">
    {#each polls as poll(poll.id)} 
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