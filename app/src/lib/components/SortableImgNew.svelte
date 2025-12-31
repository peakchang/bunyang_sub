<script>
    import { onMount } from "svelte";

    let { testval } = $props();

    onMount(() => {
        console.log('이미지 리스트 출력!!!');

        console.log(testval);
        

        // console.log($state.snapshot(testval));
    });
</script>
