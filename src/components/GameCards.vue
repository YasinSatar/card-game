<template>
   <div class="game-area">
    <h1 class="title">Poğaça <span>Nerede</span><strong>?</strong></h1>
    <h4 class="description">Açık kartlardan birini seçtikten sonra, kapalı olan karta tıklayınız.</h4>
    <div class="container">
        <app-card v-for="card in 5"></app-card>
    </div>
    <div class="container">

    </div>
   </div>


</template>

<script>
import Card from "./Card.vue"
export default{
    components:{
        appCard: Card,
    }
}
</script>

<style scoped>
.title{
    text-align:center;
    color:rosybrown;
}
.title span{
    color: mediumpurple;
}
.title strong{
    color:darkred;
}
.description{
    color:grey;
    text-align:center;
}
.container{
    margin-top:50px;
    display:flex;
    justify-content: center;
    align-items: center;
    gap:15px;
    flex-wrap: wrap;
}



</style>