<template>
  <!-- Page Container -->
  <div class="w3-content w3-margin-top" style="max-width:1400px;">

    <!-- The Grid -->
    <div class="w3-row-padding">
      <div class="w3-container w3-card w3-white w3-margin-bottom">
        <h2 class="w3-text-grey w3-padding-16">Contact Me</h2>
        <h5 class="w3-opacity"><b>Through social media or directly</b></h5><br/>
        <h5 class="w3-opacity"><b>First Name: {{info.firstname}}</b></h5>
        <h5 class="w3-opacity"><b>Last Name: {{info.lastname}}</b></h5>
        <h5 class="w3-opacity"><b>Email: <a :href="link2">{{info.email}}</a></b></h5>
        <h5 class="w3-opacity"><b>Phone Number: <a :href="'tel:'+info.phone">{{info.phone}}</a></b></h5><br/><br/>
        <div class="w3-container" style="margin-left: 3%">
          <a :href="link"> <i class="fa fa-linkedin fa-fw w3-margin-right w3-xxlarge w3-text-teal"/></a>
          <a :href="link1"> <i class="fa fa-facebook fa-fw w3-margin-right w3-xxlarge w3-text-teal"/></a>
          <a :href="link2"> <i class="fa fa-address-book fa-fw w3-margin-right w3-xxlarge w3-text-teal"/></a>
          <a :href="'tel:'+info.phone"> <i class="fa fa-phone fa-fw w3-margin-right w3-xxlarge w3-text-teal"/></a>
        </div><br/><br/>
      </div>

      <!-- End Grid -->
    </div>

    <!-- End Page Container -->
  </div>
</template>

<script>
// @ is an alias to /src

import axios from 'axios'

export default {
  name: 'Home',
  data(){
    return{
      info: [],
      link: "",
      link1: "",
      link2: ""
    }
  },
  mounted() {
    this.getUserInfo()
    this.getUserMedia()
  },
  methods:{
    getUserInfo(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_information").then(
          resp=>{
            console.log(resp)
            this.info = resp.data[0]
          }
      )
    },
    getUserMedia(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_media").then(
          resp=>{
            console.log(resp)
            this.link = resp.data[0].link
            this.link1 = resp.data[1].link
            this.link2 = resp.data[2].link
          }
      )
    }
  }
}
</script>

<style>
html,body,h1,h2,h3,h4,h5,h6 {font-family: "Roboto", sans-serif}
</style>