<script>
    import Router from 'svelte-spa-router'
    import index from './routes/index.svelte'
    import error from './routes/error.svelte'
    const routes = {
        '/': index,
        '*': error
    }
</script>

<main>
<div class="back-bg"></div>
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
