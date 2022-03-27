<script>
    export let poll;

    //reactive values
$: totalVotes = poll.votesA + poll.votesB;

</script>

<div class="poll">
    <h3>{ poll.question }</h3>
    <p>Total votes: {totalVotes}</p>
    <div class="answer">
        <div class="percent percent-a"></div>
        <span>{ poll.answerA }({ poll.votesA })</span>
    </div>
    <div class="answer">
        <div class="percent percent-b"></div>
        <span>{ poll.answerB }({ poll.votesB })</span>
    </div>
</div>

<style>

</style>

