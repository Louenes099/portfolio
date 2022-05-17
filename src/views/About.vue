<template>
  <!-- Page Container -->
  <div class="w3-content w3-margin-top" style="max-width:1400px;">

    <!-- The Grid -->
    <div class="w3-row-padding">

      <!-- Left Column -->
      <div class="w3-container w3-white w3-margin-bottom">
      <div class="w3-third w3-card-4 w3-container" style="width: 45%">
            <p class="w3-large"><b><i class="fa fa-asterisk fa-fw w3-margin-right w3-text-teal"></i>Skills</b></p>
            <div v-for="skl in skill" :key="skl.id">
              <p>{{ skl.skill }}</p>
              <div class="w3-light-grey w3-round-xlarge w3-small">
                <div class="w3-container w3-center w3-round-xlarge w3-teal" :style="{width: skl.perc}">{{skl.perc}}</div>
              </div>
            </div>
            <br>
        </div>
      <div class="w3-third w3-card-4 w3-container" style="margin-left: 10%; width: 45%">
            <p class="w3-large w3-text-theme"><b><i class="fa fa-globe fa-fw w3-margin-right w3-text-teal"></i>Languages</b></p>
            <div v-for="lg in lang" :key="lg.id">
              <p>{{ lg.lang }}</p>
              <div class="w3-light-grey w3-round-xlarge">
                <div class="w3-round-xlarge w3-teal" style="height:18px" :style="{width: lg.perc}"></div>
              </div>
            </div>
            <br>
          </div>
      </div>
      <div class="w3-container w3-card w3-white w3-margin-bottom">
        <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-code fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Programming Knowledge</h2>
        <div class="w3-container" v-for="prg in prog" :key="prg.id">
          <h5 class="w3-opacity"><b>{{ prg.know }}</b></h5>
          <p>{{ prg.detail }}</p>
          <hr>
        </div>
      </div>
        <div class="w3-container w3-card w3-white w3-margin-bottom">
          <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-suitcase fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Work Experience</h2>
          <div class="w3-container" v-for="wrk in work" :key="wrk.id">
            <h5 class="w3-opacity"><b>{{ wrk.title }} @ {{ wrk.company }}</b></h5>
            <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>{{ wrk.startdate }} - {{ wrk.enddate }}</h6>
            <p>{{ wrk.description}}</p>
            <hr>
          </div>
        </div>
        <div class="w3-container w3-card w3-white w3-margin-bottom">
          <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-mortar-board fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Education</h2>
          <div class="w3-container" v-for="ed in edu" :key="ed.id">
            <h5 class="w3-opacity"><b>{{ ed.schoolname }}</b></h5>
            <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>{{ ed.startdate }} - {{ ed.enddate }}</h6>
            <p>{{ ed.degree }}</p>
            <hr>
          </div>
        </div>
      <div class="w3-container w3-card w3-white w3-margin-bottom">
        <h2 class="w3-text-grey w3-padding-16"><i class="fa fa-certificate fa-fw w3-margin-right w3-xxlarge w3-text-teal"></i>Projects</h2>
        <div class="w3-container" v-for="prj in proj" :key="prj.id">
          <h5 class="w3-opacity"><b><a :href="prj.link"> {{ prj.name }}</a></b></h5>
          <h6 class="w3-text-teal"><i class="fa fa-calendar fa-fw w3-margin-right"></i>{{ prj.date }}</h6>
          <p>{{ prj.desc }}</p>
          <hr>
        </div>
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
      edu: [],
      prog: [],
      lang: [],
      proj: [],
      med: [],
      skill: [],
      work: [],
    }
  },
  mounted() {
    this.getUserInfo()
    this.getUserEducation()
    this.getUserProgrammingLanguage()
    this.getUserLanguage()
    this.getUserProject()
    this.getUserMedia()
    this.getUserSkills()
    this.getUserWork()
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
    getUserWork(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_work").then(
          resp=>{
            console.log(resp)
            this.work = resp.data.reverse()
          }
      )
    },
    getUserEducation(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_education").then(
          resp=>{
            console.log(resp)
            this.edu = resp.data.reverse()
          }
      )
    },
    getUserProject(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_project").then(
          resp=>{
            console.log(resp)
            this.proj = resp.data
          }
      )
    },
    getUserMedia(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_media").then(
          resp=>{
            console.log(resp)
            this.med = resp.data
          }
      )
    },
    getUserSkills(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_skills").then(
          resp=>{
            console.log(resp)
            this.skill = resp.data
          }
      )
    },
    getUserLanguage(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_lang").then(
          resp=>{
            console.log(resp)
            this.lang = resp.data
          }
      )
    },
    getUserProgrammingLanguage(){
      axios.get("https://louenes099.pythonanywhere.com/pi/api/get/user_proglang").then(
          resp=>{
            console.log(resp)
            this.prog = resp.data
          }
      )
    },
  }
}
</script>

<style>
html,body,h1,h2,h3,h4,h5,h6 {font-family: "Roboto", sans-serif}
</style>