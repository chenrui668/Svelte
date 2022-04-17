<script>
    import Demo3Child from "./Demo3Child.svelte";
    import { globalValue } from './store'

    let gv = ''
    globalValue.subscribe(v => {
        gv = v
    })
    const onChange = () => {
        globalValue.set(gv)
    }
</script>

<h1>Store</h1>
父组件：
<div>
    <input bind:value={gv}/>
    <button on:click={onChange}>修改</button>
</div>
<Demo3Child />