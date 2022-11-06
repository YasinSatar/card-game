<template>
     <div class="card">
            <img src="../assets/card-1.jpg" alt="">
        </div>
</template>
<script>

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
    box-shadow:0px 10px 10px #666;
    transform:translateY(-10px);
    transition:transform .5,box-shadow .4s;

}
.card img{
    width:100%;
    border-radius: 5px;
}
</style>