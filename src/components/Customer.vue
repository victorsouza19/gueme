<template>
  <div id="customer">
    <h4>Name: {{customer.name}}</h4>
    <hr>
    <p>{{customer.description}}</p>
    <p>Number: {{customer.number}}</p>
    <p>Email: {{customer.email}}</p>
    <p>Age: {{customer.age}}</p>
  </div>
</template>

<script>
export default {
  data(){
    return{
    }
  },
  props: {
    name: String,
    description: String,
    number: Number,
    email: String,
    age: Number,
    customer: Object
  }
}
</script>

<style scoped>
  #customer{
    background-color: #fff;
    border-radius: 0.5rem;
    padding: 2%;
    margin: 2%;
  }

</style>
