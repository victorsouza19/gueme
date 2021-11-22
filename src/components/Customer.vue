<template>
  <div :class="{'customer': !isPremium, 'customer premium': isPremium}">
    <h4>Name: {{customer.name}}</h4>
    <hr>
    <p>{{customer.description}}</p>
    <p>Number: {{customer.number}}</p>
    <p>Email: {{customer.email}}</p>
    <p v-show="showAge == true">Age with v-show: {{customer.age}}</p>
    <p v-if="showAge == true">Age: {{customer.age}}</p>
    <!-- <p v-else>Age: -- </p> -->
  </div>
</template>

<script>
export default {
  data(){
    return{
      isPremium: false
    }
  },
  props: {
    customer: Object,
    showAge: Boolean
  }
}
</script>

<style scoped>
  .customer{
    background-color: #fff;
    border-radius: 0.5rem;
    padding: 2%;
    margin: 2%;
  }

  .premium{
    background-color: rgb(0, 0, 0);
    color: rgb(197, 160, 57);
  }

</style>
