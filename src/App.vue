<template>
  <nav>
    <router-link class="item_nev p-1" to="/">Profile</router-link> |
    <router-link class="item_nev p-1" to="/gallery">Gallery</router-link>
   
  </nav>
  <router-view/>
  <footer class="py-2">
    <b>Contact : </b>
    <a class="px-2" href="http://line.me/ti/p/~toyystoryy">
       <img src="./assets/img/icon_profile/line.png" width="30">
    </a>
    <span>toyystoryy</span>
    <a class="px-2" href="https://mail.google.com/mail/?view=cm&fs=1&to=warawutt24@gmail.com" target="_blank">
      <img class="" src="./assets/img/icon_profile/gmail.png" width="30">
    </a>
    <span>warawutt24@gmail.com</span>
  </footer>
</template>

<style>
@font-face {
    font-family: font_prompt_medium;
    src: url('./assets/front/prompt/Prompt-Medium.ttf');
}
@font-face {
    font-family: font_prompt;
    src: url('./assets/front/prompt/Prompt-Regular.ttf');
}

.font-h{
  font-family: font_prompt_medium;
}
html, body {
  font-family: font_prompt;
}

#app {
  font-family: font_prompt;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 15px;
}
a {
    color: #2c3e50;
    text-decoration: none;
}
a:hover {
    color: #f59f30;
}
nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #ffffff;
  background-color: #f59f30;
  border: 3px solid #f59f30;
}

.item_nev{
  border: 3px solid #f59f30;
}
</style>
