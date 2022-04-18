<script>
    import Demo2Child from "./Demo2Child.svelte";

    let text = ''
</script>

<h1>Props</h1>
父组件：
<div>
    <input bind:value={text}/>
</div>
<Demo2Child bind:value={text} />