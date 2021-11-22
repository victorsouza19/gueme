<template>
  <div id="app">
    <h1>Curso de Vue.js</h1>
    <Customer/>
  </div>
</template>


<script>
import Customer from './components/Customer';
// import Item from './components/Item.vue';

export default {
  name: 'App',
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
</style>
