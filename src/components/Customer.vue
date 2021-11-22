<template>
  <div id="customer">
    <input type="text" :value="name">
    <h2>{{ name }}, {{age}}</h2>
    <p>{{ number }} - {{ email }} </p>
    <button>Call</button>
  </div>
</template>

<script>
export default {
  data(){
    return{
      name: "Victor",
      number: "19384473",
      email: "victor@email.com",
      age: 21
    }
  }
}
</script>

<style scoped>
  #customer{
    background-color: #fff;
    border-radius: 0.5rem;
    padding: 1rem;
    margin: 2rem;
  }

  button{
    background: #000;
    color: #fff;
    border: none;
    border-radius: 0.5rem;
    padding: 0.5rem 1rem;
  }
</style>
