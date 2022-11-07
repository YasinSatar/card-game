<template>
  <component
  @activeComponentEvent="activeComponent = $event"
  :is="activeComponent"
  >
  </component>
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
}


</style>
