<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";

	// tabs
	let items = ["Current polls", "Add new poll"];
	let activeItem = "Current polls";

</script>

<Header />
<main>
	<Tabs items={items} activeItem={activeItem}/>
</main>
<Footer />

<style>
	main {
		max-width: 960px;
		margin: 40px auto;
	}
</style>