<template>
  <div>
    <h3>Hello!</h3>
    <p>
      <app-logistics-catalog></app-logistics-catalog>
    </p>
  </div>
</template>

<script>
  import LogisticCatalog from './components/logistics_catalog/LogisticsCatalog.vue';
export default {
  components: {
    'app-logistics-catalog': LogisticCatalog
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
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

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
