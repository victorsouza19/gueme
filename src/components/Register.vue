<template>
  <div class="create">
      <h3>Register: </h3>

      <label for="">Nickname</label>
      <input type="text" placeholder="nickname" v-model="nameField">
      <small id="nameErr" v-if="nameError == true">{{ errormsg }}</small>

      <label for="">Email</label>
      <input type="email" placeholder="email" v-model="emailField">

      <label for="">Number</label>
      <input type="number" placeholder="number" v-model="numberField">

      <label for="">About you</label>
      <input type="text" placeholder="Describe you in some words" v-model="descriptionField">

      <button @click="userRegister">Register!</button>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
  .create{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    
    background: #503b3b;
    color: #fff;
    border-radius: 2rem 2rem 0  0;

    position: fixed;
    padding: 4rem;
    bottom: 0;
    width: 100%;
    min-height: 60vh;
  }

  .create h3{
    font-size: 1.8rem;
    margin-bottom: 0.5rem;
  }

  input{
    display: flex;
    align-items: center;
    justify-content: center;

    background: none;
    border: 2px solid #fff;
    border-radius: 2rem;
    color: #d9b379;
    font-size: 1.1rem;
    padding: 0.8rem;
    width: 80%;  
  }

  button{
    display: flex;
    align-items: center;
    justify-content: center;

    background: #5bce38;
    border: none;
    border-radius: 2rem;
    color: #fff;
    font-size: 1.2rem;
    padding: 1rem;

    margin-top: 3rem;
    width: 80%;  
  }


  label{
    margin: 1.5rem 0 0.3rem 0;
     
  }

  @media screen and (min-width: 768px){
  }
</style>