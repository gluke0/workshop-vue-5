<script>

import axios from "axios";

export default{
  data() {
    return{
      pizzas:[

      ],
      baseUrl: 'http://127.0.0.1:8000/api'
    }
  },
  components: {
    
  },
  mounted(){
    this.getPizza();
  },
  methods: {
    getPizza(){
      axios.get(`${this.baseUrl}/pizzas`)
      .then(res =>{
        this.pizzas = res.data.pizzas.data
      })
    }
  }
}
</script>

<template>
  
</template>

<style>
</style>
