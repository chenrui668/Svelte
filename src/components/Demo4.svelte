<script>
    const fetchData = () => new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve('加载完成')
            // reject('加载失败')
        }, 1000);
    })
</script>

<h1>Await</h1>
{#await fetchData()}
    <div>加载中...</div>    
{:then res} 
    <div style="color: blue">{res}</div>
{:catch err}
    <div style="color: red">{err}</div>
{/await}
