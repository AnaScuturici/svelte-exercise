<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import PollForm from "./components/PollForm.svelte";
	import PollList from "./components/PollList.svelte";
	import Tabs from "./shared/Tabs.svelte";

	// tabs
	let items = ["Current polls", "Add new poll"];
	let activeItem = "Current polls";

	const tabChange = (e) =>{
		activeItem = e.detail;
	};

	//polls
	let polls = [
		{
			id: 1,
			question: "Python or JS?",
			answerA: "Python",
			answerB: "JS",
			votesA: 9,
			votesB: 15,
		} 
	];

	const handleAdd = (e) => {
		const poll = e.detail;
		polls = [poll, ...polls];
		console.log(polls);
		activeItem = "Current polls";
	}

</script>

<Header />
<main>
	<Tabs items={items} activeItem={activeItem} on:tabChange={tabChange}/>
	{#if activeItem === "Current polls"}
	<PollList polls={polls}/>
	{:else if activeItem === "Add new poll"}
	<PollForm on:add={handleAdd}/>
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>