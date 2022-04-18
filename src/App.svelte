<script>
	import Demo1 from "./components/Demo1.svelte";
	import Demo2 from "./components/Demo2.svelte";
	import Demo3 from "./components/Demo3.svelte";
	import Demo4 from "./components/Demo4.svelte";
	import Demo5 from "./components/Demo5.svelte";

	const demos = [ Demo1, Demo2, Demo3, Demo4, Demo5 ]
	let currentIndex = 0
	$: Component = demos[currentIndex]
	// $: {
	// 	console.log(currentIndex)
	// }
</script>

<div class="container">
	<div class="header">
		{#each demos as _, index }
			<button on:click="{() => currentIndex = index }">demo{index + 1}</button>
		{/each}
	</div>
	<div class="content">
		<svelte:component this={Component} />
	</div>
</div>

<style>
	.container {
		padding: 60px 100px;
	}
	.content {
		margin-top: 30px;
	}
	button {
		margin-right: 30px;
	}
</style>