<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import PollForm from "./components/PollForm.svelte";
	import Tabs from "./shared/Tabs.svelte";

	// tabs
	let items = ["Current polls", "Add new poll"];
	let activeItem = "Current polls";

	const tabChange = (e) =>{
		activeItem = e.detail;
	};

</script>

<Header />
<main>
	<Tabs items={items} activeItem={activeItem} on:tabChange={tabChange}/>
	{#if activeItem === "Current polls"}
	<p>poll list goes here</p>
	{:else if activeItem === "Add new poll"}
	<PollForm />
	{/if}
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>