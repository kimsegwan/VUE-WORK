<template>
  <div id="app">
    <div class="app-content">
      <div class="main-top">
        <div class="main-top-text">
          <span class="main-top-text-01">JolTa</span>
          <span class="main-top-text-02">
            해당 홈페이지 방문을 환영합니다.
          </span>
        </div>
      </div>
      <Top v-on:menuText="menuText"/>
      <!-- <img src="./assets/logo.png"> -->
      <router-view/>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Tab01 from './components/Tab01.vue'
import Tab02 from './components/Tab02.vue'
import Top from './components/Top.vue'
import Footer from './components/Footer'
import VueRouter from 'vue-router'

var routes = [
  {path: '/', component: Tab01},
  {path: '/menu02', component: Tab02}
]

const router = new VueRouter({
  mode: 'history',
  routes
})

export default {
  name: 'App',
  router,
  data () {
    return {
      rootDataMain: 'dictoinary'
    }
  },
  methods: {
    menuText : function(text) {
      alert(text)
    }
  },
  components: {
    Tab01, Tab02, Top, Footer
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

.main-top {
  padding-top: 30px;
}

.main-top-text {
  color: #111;
}

.main-top-text-01 {
  font-size: 25px;
  font-weight: bold;
  display: block;
}

.main-top-text-02 {
  padding: 20px 0px 20px 0px;
  font-size: 20px;
  font-weight: bold;
  display: block;
}

/* #app::before { */
.app-content {
  content: '';
  /* background-image: url('./assets/tab02_back.jpg'); */
  background-image: url('./assets/main_back.jpg');
  background-size: 100% 100%;
  background-repeat: no-repeat;
  width: 100%;
  height: 100%;
  display: block;
  position: absolute;
  left: 0px;
  top: 0px;
  /* opacity: .7; */
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
