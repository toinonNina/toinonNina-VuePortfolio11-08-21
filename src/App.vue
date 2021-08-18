<template>
  <nav class="nav">
    <img class="logo" src="./assets/logo.png" alt="" />
    <input class="menu-btn" type="checkbox" id="menu-btn" />
    <label class="menu-icon" for="menu-btn"><span class="navicon">icon</span></label>
    <ul class="menu">
      <li><a href="#propos">À propos</a></li>
      <li><a href="#projets">Projets</a></li>
      <li><a href="#contact">Me contacter</a></li>
    </ul>
  </nav>
  <br><br>
  <div class="hello">
    <Home />
    <Projets />
  </div>
</template>

<script>
import Home from "@/section/Home.vue";
import Projets from "@/section/Projets.vue";
export default {
  name: "App",
  components: {
    Home,
    Projets,
  },
};
</script>

<style>
#app {
  font-family: Verdana, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #a3a3a3;
  font-size: 16px;
}
body {
  margin: 0;
  font-family: Helvetica, sans-serif;
  background: #333333 url(./assets/page-bg.jpg);
}

a {
  color: #729fcf;
}

/* nav */

.nav {
  background-color: #282828;
  box-shadow: 1px 1px 4px 0 rgba(0, 0, 0, 0.1);
  position: fixed;
  width: 100%;
  margin: 0;
  z-index: 1;
}

.nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
  overflow: hidden;
  background-color: #282828;
}

.nav li a {
  display: block;
  color: white;
  padding: 20px 20px;
  text-decoration: none;
}
/*Animation li menu*/
.nav li a::after {
  content: "";
  display: block;
  width: 100%;
  height: 2px;
  background: white;
  margin-top: 4px;
  opacity: 0;
}

.nav a:hover::after {
  opacity: 1;
}

.nav .logo {
  display: block;
  float: left;
  width: 50px;
  text-decoration: none;
  padding: 10px 20px;
}

/* menu */

.nav .menu {
  clear: both;
  max-height: 0;
  transition: max-height 0.2s ease-out;
}

/* menu icon */

.nav .menu-icon {
  cursor: pointer;
  float: right;
  color: white;
  padding: 28px 20px;
  position: relative;
  user-select: none;
}

.nav .menu-icon .navicon {
  background: white;
  display: block;
  height: 2px;
  position: relative;
  transition: background 0.2s ease-out;
  width: 18px;
  color: #282828;
}

.nav .menu-icon .navicon:before,
.nav .menu-icon .navicon:after {
  background: white;
  content: "";
  display: block;
  height: 100%;
  position: absolute;
  transition: all 0.2s ease-out;
  width: 100%;
}

.nav .menu-icon .navicon:before {
  top: 5px;
}

.nav .menu-icon .navicon:after {
  top: -5px;
}

/* menu btn */

.nav .menu-btn {
  display: none;
}

.nav .menu-btn:checked ~ .menu {
  max-height: 240px;
}

.nav .menu-btn:checked ~ .menu-icon .navicon {
  background: transparent;
}

.nav .menu-btn:checked ~ .menu-icon .navicon:before {
  transform: rotate(-45deg);
}

.nav .menu-btn:checked ~ .menu-icon .navicon:after {
  transform: rotate(45deg);
}

.nav .menu-btn:checked ~ .menu-icon:not(.steps) .navicon:before,
.nav .menu-btn:checked ~ .menu-icon:not(.steps) .navicon:after {
  top: 0;
}
.hello {
  margin: 30px 10px 10px 10px;
  background: url(./assets/body-bg.png);
  padding: 10px;
}
.divider {
  margin: 0 0 30px 0;
  width: 100%;
  height: 2px;
  background: url(./assets/divider.png) repeat-x;
  clear: both;
}
.titlesection {
  text-align: left;
  margin-bottom: 0;
  font: 400 28px/50px "Bree Serif", Georgia, serif;
}
@media (min-width: 1800px) {
  .hello {
    margin: 30px 380px;
    padding: 30px;
  }
}
@media (min-width: 930px) {
  .nav li {
    float: left;
  }
  .nav li a {
    padding: 20px 30px;
    font-size: 16px;
  }
  .nav .menu {
    clear: none;
    float: right;
    max-height: none;
  }
  .nav .menu-icon {
    display: none;
  }
}
</style>
