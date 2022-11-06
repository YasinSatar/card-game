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
  height: 232px;
  border-radius: 5px;
  border:1px solid #666;
  display: block;
  transition:transform .5s,box-shadow .6s;
  margin-top:10px;

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
</style>