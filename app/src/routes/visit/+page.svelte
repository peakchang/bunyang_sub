<script>
    import moment from "moment-timezone";
    import { onMount } from "svelte";
    let visitList = [];
    export let data;

    let startDate = moment().subtract(1, "days").format("YYYY-MM-DD");
    let endDate = moment().format("YYYY-MM-DD");

    onMount(() => {
        visitList = data.visit_list;
    });

</script>

<div class="container max-w-[1200px] py-5 px-3 mx-auto pretendard">
    <div class="mb-3 text-sm">
        <input type="date" class="input-base" bind:value={startDate} />
        <span>~</span>
        <input type="date" class="input-base" bind:value={endDate} />
        <button
            class="py-1 text-white rounded-md bg-blue-500 active:bg-blue-600"
            style="width:60px;">검색</button
        >
    </div>

    <div class="">
        <table class="w-full">
            <tbody>
                <tr>
                    <th class="in-th">IP</th>
                    <th class="in-th">이전주소</th>
                    <th class="in-th">UserAgent</th>
                    <th class="in-th">날짜</th>
                </tr>
                {#each visitList as visit}
                    <tr class="text-xs">
                        <td class="in-td text-center">
                            {visit.sv_ip}
                        </td>
                        <td class="in-td text-center p-2">
                            {visit.sv_referrer}
                        </td>
                        <td
                            class="in-td text-center p-2"
                            style="width:400px"
                        >
                            <div style="width:350px;" class="mx-auto">
                                {visit.sv_ua}
                            </div>
                        </td>
                        <td class="in-td text-center p-2">
                            {moment(visit.sv_created_at).format(
                                "YYYY-MM-DD HH:mm:ss",
                            )}
                        </td>
                    </tr>
                {/each}
            </tbody>
        </table>
    </div>
</div>
