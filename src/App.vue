<template>
  <div id="app">
    <Home />
    <Options 
      v-if="hideOptions == false" @showRegister="showRegister"
      @showAvailableFriends="showAvailableFriends" 
    />

    <Register 
      v-if="showRegisterForm == true" 
    />

    <div v-if="showFriends == true">
      <div v-for="person in people" :key="person.id">
        <People  
          :person="person" 
        />
      </div>
    </div>
  </div>
</template>


<script>
import People from './components/People';
import Options from './components/Options';
import Home from './components/Home';
import Register from './components/Register';
import _ from 'lodash';



export default {
  name: 'App',

  data(){
    return{


      nameField: "",
      emailField: "",
      numberField: 0,
      descriptionField: "",

      nameError: false,
      hideOptions: false,
      showRegisterForm: false,
      showFriends: false,

      people: [
        {
          id: 1,
          name: "Victor Souza",
          description: "Victor is a FullStack Software Developer, he is studying Vue.js at the moment",
          number: 1934584473,
          email: "victor@email.com",
        },
        {
          id: 2,
          name: "Júlia Santos",
          description: "Júlia is a Front-end Developer, she is studying Ruby on Rails at the moment",
          number: 19987546214,
          email: "juliaonrails@email.com",
        },
        {
          id: 3,
          name: "Pedro Almeida", 
          description: "Pedro is a Enginner, he works at MRV",
          number: 11987741358,
          email: "pedro.mrv@email.com",
        },
        {
          id: 4,
          name: "Ana Silva", 
          description: "Ana is an artist, she made the Monalisa art(its a joke)",
          number: 17974562836,
          email: "ana.picasso@mail.com",
        }  
      ]
    }
  },

  components: {
    Home,
    Options,
    People,
    Register
    
  },

  methods: {
    showRegister: function(){
      this.hideOptions = true;
      this.showRegisterForm = true;
      this.showFriends = false;
    },

    showAvailableFriends: function(){
      this.hideOptions = true;
      this.showRegisterForm = false;
      this.showFriends = true;
    },

    userRegister: function(){
      if(this.nameField == "" || this.nameField == " "){
        this.nameError = true;
      }else{
        this.customers.push({
          id: this.customers.length+1,
          name: this.nameField,
          email: this.emailField,
          number: this.numberField,
          description: this.descriptionField
        });

        this.nameField = "";
        this.emailField = "";
        this.numberField = "";
        this.descriptionField = "";
        this.nameError = false;
      }
    },

    deleteUsr: function($event){
      console.log($event);
      let id = $event.customerId;

      let newArr = this.customers.filter(customer => customer.id != id);
      this.customers = newArr;
    }
  },

  computed: {
    orderPeople: function(){
      return _.orderBy(this.people, ['name'], ['asc']);
    }
  }
}
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700;900&family=Outfit:wght@100;200;300;400;500;600;700;800&display=swap');

  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;

    font-family: 'Lato', sans-serif;
    font-family: 'Outfit', sans-serif;
  }

  body{
    background-color: #DFDFDF;
  }
</style>
