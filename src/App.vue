<template>
<transition-group name="slideContainer" mode="out-in">
    <component
    key="main-component"
  @activeComponentEvent="activeComponent = $event"
  :is="activeComponent"
  >
  </component>
  <canvas id="canvas" key="canvas" v-show="activeComponent == 'app-celebrate'"></canvas>
</transition-group>
</template>
<script>
 import GameCards from "./components/GameCards.vue"
 import Celebrate from "./components/Celebrate.vue"
 import Failure from "./components/Failure.vue"


export default {
    data(){
        return{
            activeComponent: "app-game-cards"
        }

    },
    components: {
        appGameCards: GameCards,
        appCelebrate: Celebrate,
        appFailure: Failure,
    }
}
</script>
<style>
body{
    font-family: sans-serif;
    overflow-x: hidden;
}

.slideContainer-enter{}
.slideContainer-enter-active{
 animation: slide-in .3s ease-in;
}
.slideContainer-leave{}
.slideContainer-leave-active{
 animation: slide-out .25s ease-out;    
}

@keyframes slide-in{
    from{
        /* transform: translateX(-100%); */
        opacity:0;
    }
    to{
        /* transform: translateX(0); */
        opacity:1;
    }
}
@keyframes slide-out{
    from{
        /* transform: translateX(0); */
        opacity:1;
    }
    to{
        /* transform: translateX(100%);  */
        opacity:0;
        height:0;
        overflow:hidden;
    }
}
</style>
