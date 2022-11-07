<template>
     <div class="card">
            <img :src="card.image" alt="">
            
        </div>
</template>
<script>
export default{
    props: ["card"],
}
</script>
<style scoped>
.card{
  width: 200px;
  height: 300px;
  border-radius: 20px;
  border:1px solid #AEAEAE;
  display: block;
  transition:transform .5s,box-shadow .6s;
  margin-top:10px;
  object-fit: scale-down;
}
.card:hover{
    cursor:pointer;
    box-shadow:0px 10px 10px rgba(0, 0, 0, 0.329);
    transform:translateY(-10px);
    transition:transform .5,box-shadow .4s;
}
.card img{
    width:100%;
    border-radius: 5px;
    user-select: none;

}

@media screen and (max-width:768px){

    .card{
        width: calc(100%/3);
        height:auto;
        flex-grow: 0;
        border:1px solid #AEAEAE;
        line-height: 0;
    }
    .card img{
        object-fit: cover;
    }
}
</style>