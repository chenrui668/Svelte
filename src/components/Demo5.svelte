<script>
    import { tweened } from 'svelte/motion';

    const progress = tweened(0);
</script>

<h1>Motion</h1>
<progress value={$progress}></progress>
{#each [0, 0.25, 0.5, 0.75, 1] as p}
    <button on:click={() => $progress = p} class="btn">
      {p*100}%
    </button>
{/each}

<style>
    progress {
        display: block;
        width: 500px;
        margin-bottom: 20px;
    }
    .btn {
        margin-right: 20px;
    }
</style>