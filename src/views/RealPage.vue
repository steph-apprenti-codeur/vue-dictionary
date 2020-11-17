<template>
    <div class="real-page">
        <div class="header">
            <input @keyup.enter="findWord()" v-model="searchVal" type="text" id="search" class="input" placeholder="Search">
            <router-link to="/">
                <b><p>cancel</p></b>
            </router-link>
            <router-view></router-view>
            
        </div>
        <div class="filter-list">
            <ul v-for="word in words" :key="word.id">
                <li class="word" v-on:scroll="hideWord()">{{word}}</li>
            </ul>
        </div>
        <div class="word-document">
            <h2>{{titre}}</h2>
        </div>
        <div class="definition">
            <h4>{{clsGram}}</h4>
            <p>definition</p>
        </div>
        <div class="text">
            {{definition}}
        </div>
    </div>
</template>
<script>
export default {
    name:"realPage",
    data() {
        return {
            message: "hello world",
            words: ['acquis', 'acquitter', 'acrobate', 'acteur', 'activite', 'blond', 'barage', 'but', 'banane', 'carotte','acquis', 'acquitter', 'acrobate', 'acteur', 'activite', 'blond', 'barage', 'but', 'banane', 'carotte'],
            mot: [{
                titre: 'mariage',
                clsGram: 'nom',
                definition: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis enim atque pariatur offic'
            },  {
                titre: 'manger',
                clsGram: 'verbe',
                definition: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis enim atque pariatur offic'
            },  {
                titre: 'dormir',
                clsGram: 'verbe',
                definition: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis enim atque pariatur offic'
            }],
            searchVal: '',
            titre: 'fee',
            clsGram: 'bgbrf',
            definition: 'rgbr',
        }
    },
    methods: {
        hideWord(){
            const word = document.querySelector(".filter-list");
            if(word.style.marginTop == 20){
                word.style.color = "red"
            }
        },
        findWord(){
            const word = document.querySelector(".filter-list");
            const docs = document.querySelector(".word-document")
            word.style.display = "none"
            docs.style.display = "block"
            this.motRechercher = this.filterList
            for(let i=0; i<this.mot.length; i++){
                if(this.searchVal == this.mot[i].titre){
                    this.titre = this.mot[i].titre
                    this.clsGram = this.mot[i].clsGram
                    this.definition = this.mot[i].definition
                }
            }

        }
    },
}
</script>

<style >
    .filter-list{
        margin-top: 60px;
    }
    li{
        list-style-type: none;
        margin-left: -20px;
        text-align: left;
        border-bottom: 1px #434343 solid;
    }
    .header{
        position: fixed;
        width: 100%;
        line-height: 8px;
        display: flex;
        justify-content: space-around;
        background-color: #285d6423;
        left: 0;
        top: 0;
        padding: 15px 5px;
        z-index: 999;
    }
    .input{
        width: 70%;
        height: 30px;
        text-align: center;
        border-radius: 5px;

    }
    .input:active,.input:hover{
        border: 1px #434343 solid;
    }
    .word-document{
        position: fixed;
        top: 60px;
        text-align: center;
        display: none;
        padding: 20px 5px;
        z-index: 9;
        left: 0;
        right: 0;
        background-color: #4378812a;
        color: rgb(250, 250, 250);
        width: 100%;
        display: none;
    }
    .definition{
        font-family: Georgia, 'Times New Roman', Times, serif;
        color: #37a2b1;
        text-align: left;
        margin-top: 180px;
        font-size: 30px;
        line-height: 20px;
    }
    .word-document h1{
        text-align: center;
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
    .text{
        text-align: left;
        margin: 0px 10px;
    }
</style>