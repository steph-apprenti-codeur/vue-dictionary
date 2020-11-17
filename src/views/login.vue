<template>
    <div>
        <router-link to="/">
            <button classe="btn">retour</button>
        </router-link>
        <router-view></router-view>
        <div :class="{flipped: flipped, notFlipped: !flipped}" class="card" @click="flippe()">
            <!--<div class="form">
            <div class="field">
                
                <input class="input" type="text" id="nom" placeholder="name">
            </div>
            <div class="field">
                
                <input class="input" type="text" id="pnom" placeholder="first name">
            </div>
            <div class="field">
                
                <input class="input"  type="password" id="password" placeholder="password">
            </div>
            <div->
                <center><button  type="submit" class="btn">log in</button></center>
            </div>-->
            <h1>back face</h1>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            flipped: false
        }
    },
    methods: {
        flippe() {
            this.flipped = !this.flipped
        }
    },
}
</script>

<style scoped>
    :root{
        --primary: #14ffaa;
    }
    .form{
        padding: 20px;
        margin: 40% auto;
    }
    .input{
        background-color: white;
        border-color: #dbdbdb;
        border-radius: 5px;
        color: #363636;;
        font-size: 25px;
    }
    .form div{
        text-align: left;
        margin: 10px;
    }
    .btn{
        padding: 5px;
        
    }
    .card{
        width: 70%;
        margin: 30% auto;
        height: 400px;
        perspective: 600px;
    }
    .card.notFlipped{
        background-color: #32d388bb; 
        transition: transform 1s;
        transform-style: preserve-3d;
    }
    .card.flipped{
        background-color: #424241;
        transform: rotateY(180deg);
        transition: transform 1s;
        perspective: 200px;
        transform-style: preserve-3d;
    }
</style>