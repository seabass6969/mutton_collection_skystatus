<script>
    import Router from 'svelte-spa-router'
    import Topbar from './component/topbar.svelte'
    import index from './routes/index.svelte'
    import error from './routes/error.svelte'
    import oasis_sheep from './routes/oasis_sheep.svelte'
    import sheep_kills from './routes/sheep_kills.svelte'
    const routes = {
        '/': index,
        '/oasis_sheep': oasis_sheep,
        '/sheep_kills':sheep_kills,
        '*': error
    }
</script>

<main>
<div class="back-bg"></div>
<Topbar />
<Router routes={routes}/>
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
</style>
