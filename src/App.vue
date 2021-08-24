<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view/> -->
    <ul class="menu-box">
    	<li v-for="item in menuList" :key="item.no">
      	{{ item.menuName }}
    	</li>
    </ul>
  <div class="contents-box">
    <Tab01></Tab01>
  </div>
  </div>
</template>

<script>
import Tab01 from './components/Tab01.vue'

export default {
  name: 'App',
  data () {
    return {
      menuList: [{no:1,menuName:'개요'}
      					,{no:2,menuName:'여행'}
                ,{no:3,menuName:'추억'}]
    }
  },
  components: {
    Tab01
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

.menu-box {
  display: block;
  float: left;
  margin: 0px;
  padding: 0px;
}

.menu-box li:first-child {
  margin-left: 0px;
}

.menu-box li {
	list-style: none;
  float: left;
  padding: 5px 20px;
  background-color: #fed;
  border: 1px solid #999;
  margin: 0px 5px;
	border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  border-bottom: none;
}

.contents-box {
  width:500px;
  height: 500px;
  border: 1px solid #999;
  float: left;
  clear: both;
  border-bottom-right-radius: 5px;
  border-bottom-left-radius: 5px;
  border-top-right-radius: 5px;
}
</style>
