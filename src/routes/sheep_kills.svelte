<script>
import Thinking from './../component/thinking.svelte'
    async function getKillsSheep(){
        let response = await fetch("https://skyblock-api.matdoes.dev/leaderboards/kills_sheep")
        let output = await response.json()
        return output
    }
    let outKillsSheep = getKillsSheep()
</script>
    <h1 class="maincolor">all the cool people of the Oasis Sheep kills</h1>
    {#await outKillsSheep}
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
