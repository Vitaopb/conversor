<template>
  <div class="conversor">
    <h2>{{moedaA}} para {{moedaB}}</h2>
    <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
    <input type="button" value="Converter" v-on:click="convert">
    <h2>{{moedaB_value}}</h2>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: "Conversor",
  props: ["moedaA", "moedaB"],

  data(){
    return{
      moedaA_value: "",
      moedaB_value: 0 + " " + this.moedaB
    };
  },
  methods: {
    convert: function() {
      let de_para = `${this.moedaA}_${this.moedaB}`
      let url = `https://free.currconv.com/api/v7/convert?q=${de_para}&compact=ultra&apiKey=ed4d281b6641af0bca49`
      console.log(url)
      console.log(typeof de_para)
      axios.get(url)
      .then((response) => {
          console.log(response.data);
          const cotacao =  this.moedaB_value = ((response.data[de_para]) * parseFloat(this.moedaA_value)).toFixed(2);
         console.log(typeof cotacao)
        });
    }
  }
}
</script>

<style scoped>
.conversor {
  max-width: 300px;
  margin-bottom: 3rem ;
  border: 1px solid red;
  padding: 1rem;  
  background: red;
  border-radius: 1rem;
  box-shadow: 0 4px 8px 0 #fff;
}

.conversor input {
  padding: .5rem;
  margin: .3rem;
  border-radius: 5px;
  outline: none;
} 
</style>
