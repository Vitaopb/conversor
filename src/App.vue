<template>
  <div id="app">
    <h1>Conversor de moedas</h1>
    <div class="linha">
    <Conversor moeda-a="USD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha">
    <Conversor moeda-a="CAD" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="CAD"/>
    </div>
     <div class="linha">
    <Conversor moeda-a="EUR" moeda-b="BRL"/>
    <Conversor moeda-a="BRL" moeda-b="EUR"/>
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue";
export default {
  name: "app",
  components: {
    Conversor
  }
}
</script>

<style>

html {
    background: #222;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  margin-top: 60px;
}

.linha {
  margin-top: 3rem;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>
