<script>
    import { globalValue } from './store'
    export let value = ''
    let gv = ''
    globalValue.subscribe(v => {
        gv = v
    })
</script>

<div>
    子组件：
    <div>
        <input bind:value={value}/>
    </div>
    <!-- store:
    <div>
        {gv}
    </div> -->
</div>
