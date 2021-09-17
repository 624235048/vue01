<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <br/>
    <span> {{message1}} </span><br/>
    <span v-text ="message2" ></span>
    <hr/>
    <span> {{counter}} </span><br/>
    <button v-on:click="counter=counter+1">+</button>
    <button v-on:click="minus">-</button>
    <hr/>
    <span> {{message3}} </span><br/>
    <input type="text" v-model="message3"/><br/>
    <input v-bind:type="inputtype"/><br/>
    <select v-model="message3">
      <option value="choice1">test 1 !!</option>
      <option value="choice2">test 2 !!</option>
      <option value="choice3">test 3 !!</option>
    </select><br/><br/>
    <textarea v-model="message3"></textarea><br/>
    
    <input v-bind:type="inputtype"/>xxxxx<br/>
    <img v-bind:src="require(`@/assets/images/`+imagename)"><br/>
    <select v-model="imagename">
      <option value="kaws.png">image 1</option>
      <option value="simpson.png">image 2</option>
      <option value="kaws2.jpg">image 3</option>
    </select><br/>
    <hr/>

    <h1/>
    <h1 v-show="isGreeting" >Hello !!! </h1>
    
    <hr/>
    {{htmlText}}<br/>
    <span v-html="htmlText"></span>
    <hr/>

   <div v-bind:key="emp.id" v-for="emp in employees">
     <b>Id :</b> {{emp.id}},<br/>
     <b>Name :</b> {{emp.name}},<br/>
     <b>Salary :</b> {{emp.Salary}},<br/><br/><br/>
   </div>
   <hr/>

  <div v-bind:key="std.studentId" v-for="std in students"> 
    <b>studentId :</b> {{std.studentId}},<br/>
    <b>firstname :</b> {{std.firstname}},<br/>
    <b>lastname :</b> {{std.lastname}},<br/>
    <b>sscore :</b> {{std.score}},<br/><br/><br/>
  </div>

  


    

    

    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  data(){
    return{
      message1: "Hello World!!",
      message2 : "Helle World Again!!!",
      message3 : "Type Here!",
      inputtype: "radio",
      imagename : "kaws.png",
      counter: 0,
      htmlText:"<b>HTML TEXT</b>&nbsp;",
      isGreeting: true,
      employees:[{"id":1,"name":"John","Salary":30000},{"id":2,"name":"Trump","Salary":10000},{"id":3,"name":"Peter","Salary":99000}],
      students:[{"studentId":624235048,"firstname": "Warinthon","lastname":"Kongjan","score":"100"},{"studentId":624235049,"firstname": "Suban","lastname":"noksong","score":"100"},{"studentId":624235050,"firstname": "Yada","lastname":"Banlates","score":"100"},{"studentId":624235052,"firstname": "wanasaree","lastname":"sahasantilarakul","score":"100"}]
    }  
  },
  methods:{
    minus: function() {
      this.counter=this.counter-1
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
