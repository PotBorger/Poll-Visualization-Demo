<script>
	import Header from "./components/Header.svelte";
	import Footer from "./components/Footer.svelte";
	import Tabs from "./shared/Tabs.svelte";
	import CreatePollForm from "./components/CreatePollForm.svelte";
  import PollList from "./components/PollList.svelte";
		// export let name;

	//tabs
	let items = ['Current Polls','Add New Poll'];
	let activeItem = 'Current Polls';
	const tabChange = (e)=>{
		console.log(e.detail)
		activeItem = e.detail;}

	const handleAdd = (e)=>{
		const poll = e.detail;
		polls = [poll,...polls];
		activeItem = 'Current Polls'
	}

	const handleVote = (e)=>{
		const {id, option} = e.detail;
		let copyOfPolls = [...polls]
		let upvotedPoll = copyOfPolls.find((poll)=> poll.id === id)
		if (option === "a"){
			upvotedPoll.votesA++;
		} 
		if (option === "b"){
			upvotedPoll.votesB++;
		}

		polls = copyOfPolls;
	}
	
</script>

<Header/>
<main>
	<Tabs {items} {activeItem} on:tabChange={tabChange}></Tabs>
	{#if activeItem === 'Current Polls'}
		<PollList on:vote={handleVote}/>
	{:else if activeItem === 'Add New Poll'}
		<CreatePollForm on:add={handleAdd}/>
	{:else}
	<p>clm</p>
	{/if}
</main>
<Footer/>

<style>
	main{
		max-width: 960px;
		margin: 40px auto
	}
</style>