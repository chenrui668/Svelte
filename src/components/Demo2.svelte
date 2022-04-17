<script>
    import Demo2Child from "./Demo2Child.svelte";
    import { globalValue } from './store'

    let text = ''
    let gv = ''
    globalValue.subscribe(v => {
        gv = v
    })
    const onChange = () => {
        globalValue.set(gv)
    }
</script>

<h1>Props</h1>
父组件：
<div>
    <input bind:value={text}/>
</div>
<!-- store:
<div>
    <input bind:value={gv}/>
    <button on:click={onChange}>修改</button>
</div> -->
<Demo2Child value={text} />