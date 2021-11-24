<template>
  <div class="person">
    <div class="person-img">
      <img src="../assets/people/2.png" alt="people-img.png">
      <h4>{{person.name}}</h4>
    </div>
    
    <div class="person-info">
      <p>{{person.description}}</p>
      <p>{{person.email}}</p>
      <p>{{person.number}}</p>
    </div>
    <div class="person-actions">
      <button>Call!</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    person: Object
  }
}
</script>

<style scoped>
  .person{
    display: flex;
    flex-direction: column;
    background: #fff;

    margin: 1rem;
    padding: 2rem;
    border-radius: 2rem;
  }

  .person h4{
    font-size: 1.8rem;
    margin: 0 1rem;
  }

  .person-img{
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;

    padding-bottom: 1rem;
  }
  .person-img img{
    max-width: 4rem;
  }

  .person-actions button{
    margin-top: 2rem;

    border: none;
    padding: 1rem 2rem;
    border-radius: 2rem;

    color: #fff;
    font-weight: 700;
    letter-spacing: 0.8px;
    background: rgb(224, 35, 82);
  }
</style>