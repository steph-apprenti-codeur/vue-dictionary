<template>
  <div class="home">
    <p class="openMenu" :class="{open: show, hide:!show}" @click="show = !show">
      <i class="fas fa-bars"></i>
    </p>
    <p class="microphone">
      <i class="fas fa-microphone"></i>
    </p>
    <div class="menu" :class="{open: show, hide:!show}">
      <br>
      <div class="header-menu">
        <img src="../assets/images/kids-book.png" height="150" class="menu-logo"><br>
      </div>
      <div class="menu-table">
        <ul>
          <li> 
            <i class="fas fa-book"></i>
            Dictionary
          </li>
          <li>
            <i class="far fa-calendar"></i>
            Word of the day
          </li>
          <li>
            <i class="fa fa-trophy"></i>
            Games
          </li>
        </ul>
        <br>
        <ul>
          <router-link to="/log-in">
            <li>
              <i class="far fa-user-circle"></i>
              Log in/Account
            </li>
          </router-link>
          <router-view></router-view>
          <li>
            <i class="far fa-clock"></i>
            Recent
          </li>
          <li>
            <i class="far fa-save"></i>
            Saved word
          </li>
          <li>
            <i class="fa fa-upload"></i>
            Upgrade
          </li>
          <li>
            <i class="fa fa-info-circle"></i>
            More
          </li>
        </ul>
      </div>
    </div>
    <HelloWorld  
      click="Get started"
      
    />
    <img src="../assets/images/kids-book.png" height="200"><br>
    <router-link to="/RealPage">
      <input type="text" id="searchBar" class="input" placeholder="Search">
    </router-link>
    <div class="scroll">
      <div class="card">
        <div class="card-image">
          <img src="../assets/images/livre.png" alt="image card" height="100" width="100">
        </div>
        Lorem ipsum dolor sit amet consectetur adipisicin
      </div>
      <div class="card">
        <div class="card-image">
          <img src="../assets/images/livre.png" alt="image card" height="100" width="100">
        </div>
        Lorem ipsum dolor sit amet consectetur adipisicin
      </div>
      <div class="card">
        <div class="card-image">
          <img src="../assets/images/livre.png" alt="image card" height="100" width="100">
        </div>
        Lorem ipsum dolor sit amet consectetur adipisicin
      </div>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '../components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    
  },
  data() {
    return {
      show: false
    }
  },
  methods: {
    
  },
}
</script>

<style scoped>
.home{
  margin-top: 20%;
}
  .scroll{
    display: flex;
    overflow-x: scroll;
    justify-content: space-around;
  }
  .card{
    margin-top: 50px;
    margin-bottom: 20px;
    width: 200px;
  }
  .menu{
    top: 0;
    position: fixed;
    height: 100vh;
    width: 70%;
    background-color: rgb(91, 119, 126);
    
  }
  .menu.hide{
    transform: translateX(-100%);
    transition: 1s;
  }
  .open{
    transform: translateX(0px);
    transition: 1s;
  }
  .openMenu.hide{
    position: absolute;
    top: 0;
    margin: 5px;
    cursor: pointer;
    font-size: 25px;
  }
  .openMenu.open{
    position: absolute;
    margin-left: 71%;
    top: 0;
    margin-top: 5px;
    cursor: pointer;
    font-size: 25px;
  }
  .menu-logo{
    border: 2px solid rgb(216, 209, 209);
    border-radius: 50%;
  }
  li{
    color: white;
    margin: 27px 5px;
    text-align: left;
    border-bottom: 1px solid white;
    font-size: 21px;
  }
  li i{
    font-size: 23px;
    position: absolute;
    left: 10px;
    font-weight: 5px;
  }
  .microphone{
    position: absolute;
    right: 0;
    top: 0;
    margin: 5px;
    font-size: 25px;
  }
</style>