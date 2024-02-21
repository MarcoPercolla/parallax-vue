<script>
import { store } from "../store.js" //state management


export default {
    name: "AppComponent",
    data() {
        return {
            store,
            xpos: 0,
            ypos: 0,


        }
    },
    methods: {
        doThings() {
            window.addEventListener("mousemove", (e) => {
                this.xpos = e.clientX - window.innerWidth / 2;
                this.ypos = e.clientY - window.innerHeight / 2;


                console.log(this.xpos, this.ypos);
            })

        }
    },
    mounted() {

        this.doThings();
    }
}
</script>

<template>
    <img class="background" :style="{ 'left': 'calc(-50% - ' + xpos + 'px)', 'bottom': 'calc(-50% - ' + ypos + 'px)' }"
        src="https://images.pond5.com/simple-star-space-background-effect-023768280_prevstill.jpeg" alt="">
    <div class="planetContainer"
        :style="{ 'left': 'calc(-80% - ' + xpos / 2 + 'px)', 'bottom': 'calc(-50% - ' + ypos / 8 + 'px)' }">
        <img class="planet" src="https://freepngimg.com/download/space/24616-8-space-planet-transparent.png" alt="">
    </div>

    <div class="planetContainer2"
        :style="{ 'left': 'calc(70% - ' + xpos / 1.5 + 'px)', 'bottom': 'calc(10% + ' + ypos / 8 + 'px)' }">
        <img class="planet" src="../../immagini/pngwing.com.png" alt="">
    </div>
</template>

<style  lang="scss"></style>