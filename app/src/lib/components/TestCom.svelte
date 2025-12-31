<script>
    import { onMount } from "svelte";
    let { testval } = $props();

    onMount(() => {
        console.log($state.snapshot(testval));
    });
</script>

<div>
    나와?
    {testval}
    {testval.length}
</div>
