<script>
    import { flip } from 'svelte/animate'
    let text
    let list = []

    const onAdd = () => {
        list = [ ...list, text ]
        text = ''
    }
    const onDelete = (index) => {
        list = list.filter((_, i) => i !== index)
    }
</script>

<h1>TodoList</h1>
<div class="row">
    <input bind:value={text} />
    <button class="btn" on:click="{onAdd}">添加</button>
</div>
{#each list as item, index (item)}
    <div class="row" animate:flip>
        <div class="text">{item}</div>
        <button class="btn" on:click="{() => onDelete(index)}">删除</button>
    </div>
{:else}
    暂无todo
{/each}

<style>
    .row {
        display: flex;
        align-items: center;
    }
    .btn {
        margin-left: 20px;
    }
    .text {
        min-width: 180px;
    }
</style>