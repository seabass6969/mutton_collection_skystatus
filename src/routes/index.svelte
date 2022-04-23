<script>
    import Thinking from './../component/thinking.svelte'
    async function getMuttonLeaderBoardCollection(){
        let response = await fetch("https://skyblock-api.matdoes.dev/leaderboards/collection_mutton")
        let output = await response.json()
        return output
    }
    let outMuttonCollection = getMuttonLeaderBoardCollection()
</script>
    <h1 class="maincolor">all the cool people of the mutton collection</h1>
    {#await outMuttonCollection}
    <Thinking />
    {:then output}
    {#each output.list as playerinfo, i}
    <h2>
    {i +1}:
<div style="color: {playerinfo.player.rank.color}">{playerinfo.player.username}</div>
    <div>collected {playerinfo.value}</div>
    </h2>
    {/each}
    {/await}
<style>
    .maincolor{
        color: #bf00c1;
    }
</style>
