<template>
  <div id="app">
    <div id="info">
      <h1>Understanding Vue.js</h1>
    </div>

    <div class="create">
      <h3>Register: </h3>

      <input type="text" placeholder="name" v-model="nameField">
      <small id="nameErr" v-if="nameError == true">Invalid name, try again!</small>
      <input type="email" placeholder="email" v-model="emailField">
      <input type="number" placeholder="number" v-model="numberField">
      <input type="text" placeholder="description" v-model="descriptionField">

      <button @click="userRegister">Register!</button>
    </div>
    

    <div v-for="(customer, index) in orderCustomers" :key="customer.id">
      <h3>{{ index+1 }}</h3>
      <Customer :customer="customer" :showAge="true" @deleteCustomer="deleteUsr($event)" />

      <!-- <div class="edit">
        <h3>Editar</h3>
        <input type="text" v-model="customer.name">
        <input type="text" v-model="customer.number">
        <input type="text" v-model="customer.email">
      </div> -->

    </div>

    <!-- 
    <Customer :customer="customer" :showAge="true"/>
    -->

    <!-- <Customer 
      :name="randomName" 
      description="Victor is a FullStack Software Developer, he is studying Vue.js at the moment"
      number="1934584473"
      email="victor@email.com"
      age= "21"
    />
    -->

  </div>
</template>


<script>
import Customer from './components/Customer';
import _ from 'lodash';
// import Item from './components/Item.vue';

export default {
  name: 'App',

  data(){
    return{
      nameField: "",
      emailField: "",
      numberField: 0,
      descriptionField: "",

      nameError: false,

      customers: [
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
    Customer
    // Item
  },

  methods: {
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
    orderCustomers: function(){
      return _.orderBy(this.customers, ['name'], ['asc']);
    }
  }
}
</script>


<style>
  body{
    background-color: #ebebeb;
  }

  #info{
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .create{
    background: #fff;
    border-radius: 0.5rem;
    padding: 1rem;
    margin: auto;
    width: 90%;

    display: flex;
    align-items: center;
    justify-content: space-evenly;
    flex-direction: column;
  }

  .create input + input {
    margin-top: 1rem;
  }

  .create button{
    background: black;
    color: #fff;

    margin: 1rem;
    border: none;
    border-radius: 0.5rem;
    padding: 0.5rem 1rem;
  }

  .edit{
    display: flex;
    align-items: center;
    justify-content: space-evenly;  
  }

  input{
    border-radius: 0.5rem;
    padding: 0.5rem 1rem;
    border: 1px solid purple;
    color: purple;
  }

  #nameErr{
    color: red;
    margin: 0.1rem 0 1rem 0;
  }
</style>
