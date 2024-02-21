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
</template>

<style  lang="scss"></style>