<template>
  <div id="app">
    <div id="nav">      
      <router-link to="/">
        <i class="fas fa-code"></i>
      </router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <transition name="fade" appear>
      <router-view/>
    </transition>
    
  </div>
</template>
<script>

export default {
  
}
</script>
<style>
.input, .textarea, .select select {
  background-color: white;
  border-color: #dbdbdb;
  border-radius: 4px;
  color: #363636;
}
body{
  margin: 0px;
  padding: 0px;
  background-color: rgb(43, 70, 85);
  color: #fff;
}
.card{
  margin: 5px;
  border-radius: 5px;
  padding: 5px;
  border: 1px solid black;
}
.fade-enter-active, .fade-leave-active{
  transition: opacity 0.5s;
  opacity: 0;
}
.fade-enter, .fade-leave-active-to{
  transition: opacity 0.5s;
  opacity: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f7f7f8;
  width: 100%;
  overflow: hidden;
  margin: 0px;
  padding: 0px;
}
a{
  text-decoration: none;
  color: #f9fbfd;
}
#nav {
  text-align: left;
  margin: 0px;
  padding: 30px;
  background-color: #434343;
  display: none;
}

#nav a {
  text-decoration: none;
  color: #fff;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
li{
  list-style: none;
}
</style>
