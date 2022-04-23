<script>
    import Thinking from './component/thinking.svelte'
    async function getMuttonLeaderBoardCollection(){
        let response = await fetch("https://skyblock-api.matdoes.dev/leaderboards/collection_mutton")
        let output = await response.json()
        return output
    }
    let outMuttonCollection = getMuttonLeaderBoardCollection()
</script>

<main>
    <div class="back-bg"></div>
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
</main>

<style>
    .back-bg{
    background-image: url('/background/main.webp');
    background-repeat: no-repeat;
    background-size: cover;

    filter: blur(2px);
    position: fixed;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: -1;
    }
    .maincolor{
        color: #bf00c1;
    }
</style>
