<template>
  <div id="app">
    <div class="app-content">
      <Top v-on:menuText="menuText"/>
      <!-- <img src="./assets/logo.png"> -->
      <router-view/>
    </div>
  </div>
</template>

<script>
import Tab01 from './components/Tab01.vue'
import Tab02 from './components/Tab02.vue'
import Top from './components/Top.vue'

var routes = [
  {path: '/menu01', components: Tab01},
  {path: '/menu02', components: Tab02}
]

var router = new VueRouter({
  routes
})

export default {
  name: 'App',
  data () {
    return {

    }
  },
  methods: {
    menuText : function(text) {
      alert(text)
    }
  },
  components: {
    Tab01, Tab02, Top
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
  overflow: hidden;
  position: relative;
  font-family: "맑은 고딕";
}

#app::before {
  content: '';
  background-image: url('./assets/main_back.jpg');
  background-size: cover;
  width: 100%;
  height: 100%;
  display: block;
  position: absolute;
  left: 0px;
  top: 0px;
  opacity: .7;
}

.app-content{
  position:relative;
}

.slide-menu-bar {
  width: 10px;
  border: 1px solid #999999;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;
  overflow: hidden;
  position: relative;
  transition: width .5s;
  opacity: .5;
  margin-top: 20px;
}

.slide-menu-box {
  margin: 0px;
  padding: 0px;
  overflow: hidden;
  width: 90%;
  float: left;
  height: 40px;
}

.slide-menu-box li {
  list-style: none;
  float: left;
  display: block;
  padding: 0px 25px;
  margin: 5px 0px;
  line-height: 30px;
  font-size: 15px;
  font-weight: bold;
  cursor: pointer;
  border-right: 1px solid #999;
  font-style: "";
}

.menu_slide_btn {
  width: 10px;
  height:40px;
  position: absolute;
  right: 0px;
  background-color: rgb(189, 189, 235);
}

.menu-box {
  display: block;
  float: left;
  margin: 0px;
  padding: 0px;
  margin-top: 15px;
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
  overflow: hidden;
}
</style>
