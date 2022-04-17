<script>
    import { globalValue } from './store'
    let gv = ''
    globalValue.subscribe(v => {
        gv = v
    })
</script>

<div>
    子组件：
    <div>
        {gv}
    </div>
</div>
