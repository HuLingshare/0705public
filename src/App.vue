<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HelloWorld/>
    <Table1/>
    <Table2/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Table1 from './components/Table1.vue'
import Table2 from './components/Table2.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Table1,
    Table2
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
</style>
