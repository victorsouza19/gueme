<template>
  <div :class="{'customer': !isPremium, 'customer premium': isPremium}">
    <h4>Name: {{customer.name}}</h4>
    <hr>
    <p>{{customer.description}}</p>
    <p>Number: {{customer.number}}</p>
    <p>Email: {{ emailProcess }}</p>

    <!-- <p v-show="showAge == false">Age with v-show: {{customer.age}}</p>
    <p v-if="showAge == true">Age: {{customer.age}}</p>
    <p v-else>Age: -- </p> -->

    <button @click="setColor($event)">Set color!</button>
    <button @click="sendDeleteEvent">Delete</button>
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
  },

  methods: {
    setColor: function($event){
      console.log($event);
      this.isPremium = !this.isPremium;
    },
    sendDeleteEvent: function(){
      console.log("Send delete from child!")
      this.$emit("deleteCustomer", {customerId: this.customer.id, component: this});
    }
  },

  computed: {
    emailProcess: function(){
      return this.customer.email.toUpperCase();
    }
  }
}
</script>

<style scoped>
  .customer{
    background-color: #fff;
    border-radius: 0.5rem;
    border: 1px solid purple;
    padding: 2%;
    margin: 2%;
  }

  .premium{
    background-color: rgb(0, 0, 0);
    color: rgb(197, 160, 57);
  }

</style>
