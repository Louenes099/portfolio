<template>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
  <link rel='stylesheet' href='https://fonts.googleapis.com/css?family=Roboto'>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
  <div id="w3-bar w3-border w3-green" style="background-color: #009688; height: 80px">
    <h3 class="w3-bar-item w3-left" style="margin-bottom: 1%; margin-top: 1%; margin-left: 1%"><b>Shariful Islam</b></h3>
    <router-link class="w3-bar-item w3-button w3-right" style="margin-bottom: 1%; margin-top: 1%" to="/contact"><b>Contact</b></router-link>
    <router-link class="w3-bar-item w3-button w3-right" style="margin-bottom: 1%; margin-top: 1%" to="/about"><b>Details</b></router-link>
    <router-link class="w3-bar-item w3-button w3-right" style="margin-bottom: 1%; margin-top: 1%" to="/"><b>Home</b></router-link>
  </div>

  <router-view/>
  <footer class="w3-container w3-teal w3-center w3-margin-top">
    <p>Find me on social media.</p>
    <a href="https://www.facebook.com/5h4r1fu1/" target="_blank"><i class="fa fa-facebook-official w3-hover-opacity"></i></a>&nbsp;
    <a href="https://www.linkedin.com/in/islam-shariful-2001/" target="_blank"><i class="fa fa-instagram w3-hover-opacity"></i></a>&nbsp;
    <a href="https://www.instagram.com/5h4r1fu1/" target="_blank"><i class="fa fa-snapchat w3-hover-opacity"></i></a>&nbsp;
    <a href="https://twitter.com/Louenes099" target="_blank"><i class="fa fa-twitter w3-hover-opacity"></i></a>&nbsp;
    <a href="https://www.linkedin.com/in/islam-shariful-2001/" target="_blank"><i class="fa fa-linkedin w3-hover-opacity"></i></a>&nbsp;
    <p>Powered by <a href="https://www.linkedin.com/in/islam-shariful-2001/" target="_blank">Shariful Islam</a></p>
  </footer>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
