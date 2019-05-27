<template>
  <div id="app">
    <header class="cal_header"> Calculator </header>
    <section class='autor'>By YingYing </section>>
    <div class='calculator'>
      <Calculator />
    </div>
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'app',
  components: {
    Calculator
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
header{
  color: #665dc0 ;
  text-align: center;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-style: oblique;
  font-size: 30px;


}
section{
  padding: 15px;
  padding-left: 100px;
  color: rgb(49, 85, 85);
  text-align: center;
  font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-style: oblique;
}
.calculator{
  border: #4bcfd8;
  border-style: solid;
  -webkit-border-radius: 1rem;
  -moz-border-radius: 1rem;
  -ms-border-radius: 1rem;
  -o-border-radius: 1rem;
  border-radius: 1rem;
  -webkit-box-shadow: 1rem 1rem 0.5rem #ccc;
  box-shadow: 1rem 1rem 0.5rem #ccc;
  max-width: 550px;
  margin: auto;
  background-color: #4bcfd8;
}
</style>
