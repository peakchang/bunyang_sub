<script>
    import { onMount } from "svelte";
    import { back_api, back_api_origin } from "$lib/const";
    import { setImg } from "$lib/lib.js";

    let { siteData } = $props();

    // 구버전 변수
    let mainImgList = $state([]);
    let dataAosList = [];
    let bannerImgList = [];
    let bannerSwiper;
    let customerName = "";
    let customerPhone = "";

    onMount(() => {
        if (siteData.ld_main_img) {
            mainImgList = siteData.ld_main_img.split(",");
        }
    });
</script>

{#each mainImgList as mainImg, idx}
    {#if mainImg}
        <div class="mb-5">

            <img src={setImg(mainImg)} alt="" class="w-full" />
        </div>
    {/if}
{/each}
