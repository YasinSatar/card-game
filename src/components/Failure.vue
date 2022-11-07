<template>
    <div class="container">
        <h1>Game Over</h1>
        <button @click="newGame">New Game</button>
    </div>
  
</template>

<script>
export default{
    methods:{
        newGamer(){

        }
    },
}
</script>

<style scoped>
.container{
    position:absolute;
    top:0;
    left:0;
    width: 100%;
    height: 100%;
    display:flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background-color:lightcoral;
}
.container h1{
    text-align: center;
    font-size: 5rem;
    color:white;
}

.container button{
    width:200px;
    background-color:#fff;
    color:black;
    border:none;
    height:50px;
    font-size:15px;
    border-radius: 5px;
    outline:none;
    cursor:pointer;
    transition:all .5s;
}

.container button:hover{
    transition:all .5s;
    transform: translateY(-5px);
    box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.35);
}
</style>