<template>
  <div class="options">
    <h3>Hello, welcome to Gueme, we are happy to see you here!</h3>
    <p>Choose what you want :)</p>

    <div class="btn-options">
      <button @click="findAFriend">I want to find a friend</button>
      <button @click="foundByFriend">I want to be found by a friend</button>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    findAFriend: function(){
      console.log("Show friends available!");
      this.$emit("showAvailableFriends", {component: this});
    },

    foundByFriend: function(){
      console.log("Show register form!");
      this.$emit("showRegister", {component: this});
    }
  }
}
</script>

<style scoped>
  .options{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
    text-align: center;

    background: #fff;
    color: #000;
    border-radius: 2rem 2rem 0  0;

    position: fixed;
    padding: 4rem;
    bottom: 0;
    width: 100%;
    min-height: 60vh;
  }

  .options h3{
    font-size: 1.8rem;
  }

  .options p{
    font-size: 1.4rem;
  }

  .btn-options{
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    width: 100%;
  }

  .btn-options button{
    display: flex;
    align-items: center;
    justify-content: center;

    font-weight: 600;
    background: #503b3b;
    border: none;
    border-radius: 2rem;
    color: #fff;
    font-size: 1.2rem;
    padding: 1rem;
    width: 100%;

  }

  .btn-options button + button{
    margin-top: 2rem;   

    background: none;
    border: 2px solid #503b3b;
    border-radius: 2rem;
    color: #503b3b;

  }

  @media screen and (min-width: 768px){
    .btn-options{
    flex-direction: row;
    }

    .btn-options button + button{
      margin-top: 0;   
    }

    .btn-options button{
      margin: 0 1.5rem;
    }
  }
</style>