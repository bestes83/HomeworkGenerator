<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="https://vuejs.org/images/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->

    <input
      type="radio"
      name="equationType"
      @click="generateEquations('add')"
    />Addition

    <input type="radio" name="equationType" />Subtraction
  </div>
  <div>
    <div v-for="equation in equations" style="display: inline-block">
      <div class="number" style="margin-left: 17px; width: 100px">
        {{ equation.Number1 }}
      </div>
      <div style="display: inline-block">{{ equation.operator }}</div>
      <div class="number" style="display: inline-block; width: 100px">
        {{ equation.Number2 }}
      </div>
      <div style="border-bottom: solid black 2px; width: 100px"></div>
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  // components: {
  //   HelloWorld,
  // },
  data() {
    return {
      equations: [],
    };
  },
  // mounted() {
  //   this.generateEquations('add');
  // },
  methods: {
    //selectEquationType(e, type) {},
    generateEquations(type) {
      var equation = { Number1: 15, Number2: 14, operator: '+' };
      this.equations.push(equation);
      for (var i = 0; i < 20; i++) {
        this.equations.push({ Number1: 15, Number2: 14, operator: '+' });
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.number {
  margin: 10px;
}
</style>
