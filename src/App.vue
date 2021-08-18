<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view/>
    <div v-for="item in list" :key="item.key">
      {{ item.value }}
    </div>    
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      list: [{key: '1', value: '첫번째'}, {key: '2', value: '두번째'}]
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
</style>
