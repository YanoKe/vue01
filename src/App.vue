<template>

    <div class="app" v-bind:class="{ 'hide-after': !showAfter }">
        <h1>该页面为实验性测试</h1>
        <oneword />
    </div>
</template>

<script lang="ts" setup >
import oneword from './components/oneword.vue'
import {ref,onMounted} from 'vue'
defineOptions({
    name: "word",
})

const showAfter = ref(true)

onMounted(() => {
    setTimeout(() => {
        showAfter.value = false
    }, 1000)
})

</script>

<style scoped >
@import url('https://fonts.googleapis.com/css2?family=Quicksand&display=swap');
    :root {
            font-size: 15px;
        }
        .app.hide-after::after {
            display: none !important;
        }
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            overflow: hidden;
            
        }

        h1{
            transform: scale(1);
            animation: 1.5s move ;
            transform: translateY(-40vh) scale(0.5);
            white-space: nowrap;
            z-index: 1000;
        }
        @keyframes  move {
            from{
                transform: translateY(0) scale(1);
            }
            to{
                transform: translateY(-40vh) scale(0.5);
            }
            
        }
        .app {
            display: flex;
            flex-direction: column;
            font-family: 'Quicksand', sans-serif;
            margin: 0;
            min-height: 100vh;
            background-color: #e493d0;
            background-image:
                radial-gradient(closest-side, rgba(235, 105, 78, 1), rgba(235, 105, 78, 0)),
                radial-gradient(closest-side, rgba(243, 11, 164, 1), rgba(243, 11, 164, 0)),
                radial-gradient(closest-side, rgba(254, 234, 131, 1), rgba(254, 234, 131, 0)),
                radial-gradient(closest-side, rgba(170, 142, 245, 1), rgba(170, 142, 245, 0)),
                radial-gradient(closest-side, rgba(248, 192, 147, 1), rgba(248, 192, 147, 0));
            background-size:
                130vmax 130vmax,
                80vmax 80vmax,
                90vmax 90vmax,
                110vmax 110vmax,
                90vmax 90vmax;
            background-position:
                -80vmax -80vmax,
                60vmax -30vmax,
                10vmax 10vmax,
                -30vmax -10vmax,
                50vmax 50vmax;
            background-repeat: no-repeat;
            animation: 10s movement linear infinite;
        }
    
        .app::after {
            content: '';
            display: block;
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            transition: opacity 1s ;
            z-index: 100;
        }
        div {
            position: relative;
            z-index: 10;
            display: flex;
            min-height: 100vh;
            width: 100%;
            justify-content: center;
            align-items: center;
            font-size: 6vw;
            color: transparent;
            text-shadow:
                0px 0px 1px rgba(255, 255, 255, .6),
                0px 4px 4px rgba(0, 0, 0, .05);
            letter-spacing: .2rem;
        }
    
        @keyframes movement {
    
            0%,
            100% {
                background-size:
                    130vmax 130vmax,
                    80vmax 80vmax,
                    90vmax 90vmax,
                    110vmax 110vmax,
                    90vmax 90vmax;
                background-position:
                    -80vmax -80vmax,
                    60vmax -30vmax,
                    10vmax 10vmax,
                    -30vmax -10vmax,
                    50vmax 50vmax;
            }
    
            25% {
                background-size:
                    100vmax 100vmax,
                    90vmax 90vmax,
                    100vmax 100vmax,
                    90vmax 90vmax,
                    60vmax 60vmax;
                background-position:
                    -60vmax -90vmax,
                    50vmax -40vmax,
                    0vmax -20vmax,
                    -40vmax -20vmax,
                    40vmax 60vmax;
            }
    
            50% {
                background-size:
                    80vmax 80vmax,
                    110vmax 110vmax,
                    80vmax 80vmax,
                    60vmax 60vmax,
                    80vmax 80vmax;
                background-position:
                    -50vmax -70vmax,
                    40vmax -30vmax,
                    10vmax 0vmax,
                    20vmax 10vmax,
                    30vmax 70vmax;
            }
    
            75% {
                background-size:
                    90vmax 90vmax,
                    90vmax 90vmax,
                    100vmax 100vmax,
                    90vmax 90vmax,
                    70vmax 70vmax;
                background-position:
                    -50vmax -40vmax,
                    50vmax -30vmax,
                    20vmax 0vmax,
                    -10vmax 10vmax,
                    40vmax 60vmax;
            }
        }


</style>
