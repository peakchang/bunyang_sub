<script>
    import TestCom from "$lib/components/TestCom.svelte";
    import { onMount } from "svelte";

    let testval = $state([]);

    let gogo = "1,2,3,4,5,6,7,8,9";
    onMount(() => {
        testval = gogo.split(",");
    });
</script>

<TestCom {testval}></TestCom>
