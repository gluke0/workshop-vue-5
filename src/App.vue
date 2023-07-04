<script>

import axios from "axios";

export default{
  data() {
    return{
      pizzas:[

      ],
      baseUrl: 'http://127.0.0.1:8000'
    }
  },
  components: {
    
  },
  mounted(){
    this.getPizza();
  },
  methods: {
    getPizza(){
      axios.get(`${this.baseUrl}/api/pizzas`)
      .then(res =>{
        this.pizzas = res.data.pizzas;
      })
    }
  }
}
</script>

<template>
  

  <div class="mt-4" v-for="(pizza, index) in pizzas" :key="index">

  <div>
    <p class="card-title mb-0 "> <strong> {{ pizza.name }} </strong> </p>
    <p class="mb-0 "> {{ pizza.price }} € </p>
  </div>

  </div>

</template>

<style>
</style>
