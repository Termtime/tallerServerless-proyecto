<template>
  <div id="app">
    <div class="body bg-super-dark" >
      <div id="container">
        <div id="header">
          <AppBar />
        </div>
        <div>
          <router-view :key="$route.path" class="router-view" />
        </div>
      </div>
      <Footer />
    </div>
  </div>
</template>

<script>
import AppBarBase from "./components/AppBar.vue";
import { withFirebase } from "./components/HOC/FirebaseProvider.js";
import Footer from "./components/Footer.vue";

const AppBar = withFirebase(AppBarBase);
export default {
  components: { AppBar, Footer }
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Mukta:wght@300&display=swap");

#app {
  font-family: "Mukta", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  padding: 0;
  margin: 0;
}

html,
body {
  background-color: #111;
  font-family: "Mukta", sans-serif;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.left {
  align-self: flex-start;
}

.inline-right-margin {
  margin-right: 10px;
}

.center {
  justify-content: center;
  align-content: center;
}

.bg-super-dark {
  background-color: #111;
}

.link {
  cursor: pointer;
}
.loginCard {
  width: 400px;
  margin: 100px 100px 20px 100px;
  padding: 20px;
  text-align: left;
  border-radius: 5px;
}

.column {
  display: flex;
  flex-direction: column;
}

.top-right-corner {
  justify-content: flex-end;
  justify-self: flex-end;
  position: relative;
  right: 2px;
  top: 15px;
  margin-bottom: -25px;
}

.icon-black {
  color: black;
  transition-duration: 0.2s;
}

.icon-yellow {
  color: yellow;
  transition-duration: 0.2s;
}

.icon-red {
  color: crimson;
  transition-duration: 0.2s;
}
.icon-red:hover {
  color: #933;
}

.icon-dark-red {
  color: #933;
  transition-duration: 0.2s;
}
.icon-lg {
  font-size: 2em;
  z-index: 2;
}
.flex-container {
  display: flex;
}

/* #container {
  display: table;
  width: 100%;
  height: 100%;
  margin: 0;
}
footer {
  width: 100%;
  height: 150px; 
  display: table-row;
} */

.footer {
  justify-content: center;
}
.column {
  display: flex;
  flex-direction: column;
}

.footer-container {
  width: 80%;
  display: flex;
  justify-content: space-around;
}

.reactive {
  transition-duration: 0.2s;
}
.reactive:hover {
  transform: scale(1.2);
}

.body {
  position: relative;
  min-height: 100vh;
}

#container {
  padding-bottom: 160px;
}
footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 160px;
}
</style>
