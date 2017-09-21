<template>
    <div id="container" class="level">
        <div class="level-item">
            <div id="app">
                <main>
                    <router-view></router-view>
                </main>
                <footer-reel/>
            </div>
        </div>
    </div>
</template>

<script>
import FooterReel from './components/FooterReel'

import './bulma.scss'

export default {
    components: {
        'footer-reel': FooterReel,
    },
}
</script>

<style lang="less">
@import './vars';

:root,
body,
#container {
    height: 100%;
    width: 100%;
    margin: 0;
}

#container {
    background: #6f2424;
    background: linear-gradient(to bottom right, #6f2424, #350c0c);
}

#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    padding-bottom: @footer-height;
    height: 75vh;
    width: 70vw;
    box-shadow: 0 0 80px 5px rgba(0, 0, 0, 0.4);
}

main {
    height: 100%;
    color: white;
    background: #1e1e1e;
}
</style>
