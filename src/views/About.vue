<template>
    <div class="about">
        
        <helloWorld
            msg="Bienvenu sur votre Vue.js App"
        />
        <img alt="Vue logo" src="../assets/images/livre.png" class="image" height="200" width="200">
    </div>
</template>


<script>

import HelloWorld from '../components/HelloWorld.vue'
export default {
    name:"about",
    components:{
        HelloWorld
    },
    data() {
        return {
            
        }
    },
    
}
</script>

<style>

</style>
