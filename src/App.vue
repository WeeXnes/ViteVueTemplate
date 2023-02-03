<template>
  <div id="navBar">
    <div class="navItem navItemMaster" id="navBarMenuButton" @click="toggleNavBar">
      <img id="navBarToggleIcon" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b2/Hamburger_icon.svg/1200px-Hamburger_icon.svg.png" class="navImage"/>
    </div>
    <router-link to="/" class="navItem">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/34/Home-icon.svg/2048px-Home-icon.svg.png" class="navImage"/>
      <p class="navText">Home</p>
    </router-link>
    <!--<router-link to="/about" class="navItem">
      <img src="http://cdn.onlinewebfonts.com/svg/img_60160.png" class="navImage"/>
      <p class="navText">Performance</p>
    </router-link> -->
    <router-link to="/about" class="navItem">
      <img src="https://cdn-icons-png.flaticon.com/512/126/126472.png" class="navImage"/>
      <p class="navText">Settings</p>
    </router-link>
  </div>
  <router-view/>
</template>


<script>
export default {
  methods: {
    toggleNavBar(){
      document.getElementById("navBar").classList.toggle("activeNavBar")
      let menuIcon = document.getElementById("navBarToggleIcon")
      menuIcon.classList.toggle("navBarAnimation")
      let navBarTexts = document.getElementsByClassName("navText")
      for (var i = 0; i < navBarTexts.length; i++) {
        navBarTexts[i].classList.toggle("activeNavText")
      }
      setTimeout( () => {
        menuIcon.classList.toggle("navBarAnimation")
      }, 200)
    }
  }
}
</script>
<style>
.router-link-exact-active{
  background: rgba(30,10,30,.4) !important;
}
@-webkit-keyframes menuAnim {
  0% {
    padding-left: 0;
  }
  50%{
    padding-left: 20px;
  }
  100% {
    padding-left: 0;
  }
}
.navText{
  color: white;
  text-decoration: none;
  transition: opacity .2s;
  font-size: 18px;
  opacity: 0;
}
#navBarToggleIcon{
  transition: .2s;
}
.navBarAnimation{
  animation-name: menuAnim;
  animation-iteration-count: 1;
  animation-duration: .2s;
}
.navItem{
  -webkit-backdrop-filter: saturate(50%) blur(8px);
  backdrop-filter: saturate(50%) blur(8px);
  background: transparent;
  cursor: pointer;
  border-radius: 5px;
  margin: 5px;
  height: 25px;
  padding: 10px;
  align-items: center;
  display: flex;
  vertical-align: middle;
  animation: gradient 15s ease infinite;
  width: auto;
}
.navItemMaster{
  background: transparent;
}
.navImage{
  filter: invert();
  height: 30px;
  padding-right: 10px;
}
.activeNavBar{
  width: 180px !important;
}
.activeNavText{
  opacity: 1;
}
#navBar{
  z-index: 40;
  box-shadow: 0 0 10px rgb(25, 25, 26);
  overflow: hidden;
  transition: .2s;
  position: fixed;
  width: 60px;
  height: 100%;
  -webkit-backdrop-filter: saturate(50%) blur(8px);
  backdrop-filter: saturate(50%) blur(8px);
  background: rgba(36,36,36,.7);
  top: 0;
  left: 0;
}
</style>
