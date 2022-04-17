<script>
    const fetchData = () => new Promise(resolve => {
        setTimeout(() => {
            resolve('加载完成')
        }, 1000);
    })
</script>

<h1>Await</h1>
{#await fetchData()}
    <div>加载中...</div>    
{:then res} 
    <div>{res}</div>
{/await}
