<template>
   <div class="game-area">
    <p>{{/*answer*/}}</p>
    <h1 class="title">Which is the <span>Right</span><strong>?</strong></h1>
    <h4 class="description">After selecting one of the cards open, click on the card that is closed.</h4>
    <div class="container">
        <transition-group name="rotate-all" class="card-container" appear>
        <app-card 
        :key="card.id"
        :class="{'selected' : selectedCard == card.id}"
        @click.native="selectedCard = card.id"
        v-for="card in cards" 
        :card="card"></app-card
        >
    </transition-group>
    </div>
    <div class="container">
     <transition  name="rotate" mode="out-in">
        <component
        @click.native="showCard(answer)"
        :card="answer"
        :is="activeCard"
        :class="{'answer' : activeCard != 'app-default-card' }"
        >
        </component>
     </transition>
      
    </div>
   </div>


</template>

<script>
import Card from "./Card.vue"
import DefaultCard from "./DefaultCard.vue"
export default{
    components:{
        appCard: Card,
        appDefaultCard: DefaultCard,
    },
    data(){
        return{
            selectedCard:null,
            answer: {},
            activeCard: "app-default-card",
            cards: [
                {id:1,component: "app-card", image: "/src/assets/cards/card-a.png"},
                {id:2,component: "app-card", image: "/src/assets/cards/card-j.png"},
                {id:3,component: "app-card", image: "/src/assets/cards/card-q.png"},
                {id:4,component: "app-card", image: "/src/assets/cards/card-k.png"},
                {id:5,component: "app-card", image: "/src/assets/cards/card-10.png"},
                
            ],
        }
    },
    created(){
        let answer = Math.ceil(Math.random() * this.cards.length)-1;
        this.answer= this.cards[answer];
    },
    methods:{
        showCard(answer){

            if(this.selectedCard == null){
                alert("İlk olarak bir kart seçiniz!")
            }else{
                this.activeCard=answer.component;
                setTimeout(()=>{
                    if(answer.id == this.selectedCard){
                    this.$emit("activeComponentEvent", "app-celebrate");
                }else{
                    this.$emit("activeComponentEvent", "app-failure");
                }
                },1500);
               
                
            }
            
        }
    }

}
</script>

<style scoped>
.title{
    text-align:center;
    color:rgb(82, 218, 195);
}
.title span{
    color: rgb(46, 144, 151);
}
.title strong{
    color:rgb(0, 111, 139);
}
.description{
    color:grey;
    text-align:center;
}
.container, .card-container{
    margin-top:50px;
    display:flex;
    justify-content: center;
    align-items: center;
    gap:15px;
    flex-wrap: wrap;
}
@media screen and (max-width:768px){

    .card-container{

}
}
.selected{
    box-shadow:0px 0px 30px rgb(75, 252, 243)!important;
    transition:box-shadow .5s;
    transform:translateY(-10px);
}
.card.answer{
 box-shadow:0px 0px 30px rgb(75, 252, 243)!important;
pointer-events: none !important;
}
.card.answer:hover{
 box-shadow:0px 0px 30px rgb(75, 252, 243)!important;
 transform:translateY(0px) !important;
}
/*** Open Card for Animation*/
.rotate-all-enter{}
.rotate-all-enter-active{
animation: rotate-all ease-in-out 1.5s forwards;
}
.rotate-all-leave{

}
.rotate-all-leave-active{

}

@keyframes rotate-all {
    from{
        transform: rotateY(0);
    }
    to{
        transform: rotateY(1080deg);
    }
}

/*** Animation for Closed Card  */
.rotate-enter{}
.rotate-enter-active{
animation: rotate-in .5s  ease-in-out forwards;
}
.rotate-leave{

}
.rotate-leave-active{
    animation: rotate-out .5s ease-in-out  forwards;
}
@keyframes rotate-in {
    from{
        transform: rotateY(90deg);
    }
    to{
        transform: rotateY(0deg);
    }
}
@keyframes rotate-out {
    from{
        transform: rotateY(0deg);
    }
    to{
        transform: rotateY(90deg);
    }
}
</style>