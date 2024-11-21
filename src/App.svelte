<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
  import Tabs from "./shared/Tabs.svelte";
	export let name;

	//tabs
	let items = ['Current Polls','Add New Poll'];
	let activeItem = 'Current Polls';
	
</script>

<Header/>
<main>
	<Tabs {items} {activeItem}></Tabs>
</main>
<Footer/>

<style>
	main{
		max-width: 960px;
		margin: 40px auto
	}
</style>