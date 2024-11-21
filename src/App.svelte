<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
  import Tabs from "./shared/Tabs.svelte";
	export let name;

	//tabs
	let items = ['Current Polls','Add New Poll'];
	let activeItem = 'Current Polls';
	const tabChange = (e)=>{activeItem = e.detail;}
</script>

<Header/>
<main>
	<Tabs {items} {activeItem} on:tabChange={tabChange}></Tabs>
	{#if activeItem === 'Current Polls'}
		<p>Polls components will be here</p>
	{/if}
</main>
<Footer/>

<style>
	main{
		max-width: 960px;
		margin: 40px auto
	}
</style>