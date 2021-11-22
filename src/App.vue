<template>
  <div id="app">

    <div id="info">
      <h1>Curso de Vue.js</h1>
      <input type="text" v-model="customer.name">
    </div>

    <Customer :customer="customer" :showAge="true"/>
    <Customer :customer="customer" :showAge="false"/>
    <Customer :customer="customer" :showAge="true"/>

    <!-- <Customer 
      :name="randomName" 
      description="Victor is a FullStack Software Developer, he is studying Vue.js at the moment"
      number="1934584473"
      email="victor@email.com"
      age= "21"
    />
    <Customer 
      name="Júlia Santos" 
      description="Júlia is a Front-end Developer, she is studying Ruby on Rails at the moment"
      number="19987546214"
      email="juliaonrails@email.com"
      age= "27"
    />
    <Customer 
      name="Pedro Almeida" 
      description="Pedro is a Enginner, he works at MRV"
      number="11987741358"
      email="pedro.mrv@email.com"
      age= "33"
    /> -->

  </div>
</template>


<script>
import Customer from './components/Customer';
// import Item from './components/Item.vue';

export default {
  name: 'App',

  data(){
    return{
      randomName: "Lorem Ipsum",

      customer: {
        name: "Victor Souza",
        description: "Victor is a FullStack Software Developer, he is studying Vue.js at the moment",
        number: "1934584473",
        email: "victor@email.com",
        age: "21"
      }
    }
  },

  components: {
    Customer,
    // Item
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

  #info input{
    border-radius: 0.5rem;
    padding: 0.5rem 1rem;
    border: 1px solid purple;
    color: purple;
  }
</style>
