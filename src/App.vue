<template>
  <div id="app">
    <div class="slide-menu-bar" id="slide-menu-bar">
			<ul class="slide-menu-box">
    		<li v-for="item in menuList" :key="item.no" @click="menuChange(item.no)">
      		{{ item.menuName }}
    		</li>
      </ul>
      <div class="menu_slide_btn" @click="menuSlideSizing()" @mouseover="menuSlideSizing()"></div>
    </div>
    <div>

    </div>
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view/> -->
    <ul class="menu-box">
    	<li v-for="item in menuList" :key="item.no" @click="menuChange(item.no)">
      	{{ item.menuName }}
    	</li>
    </ul>
  <div class="contents-box">
    <Tab01 v-if="menuNo == 1"></Tab01>
    <Tab02 v-if="menuNo == 2"></Tab02>
  </div>
  </div>
</template>

<script>
import Tab01 from './components/Tab01.vue'
import Tab02 from './components/Tab02.vue'

export default {
  name: 'App',
  data () {
    return {
      menuList: [{no:1,menuName:'개요'}
      					,{no:2,menuName:'여행'}
                ,{no:3,menuName:'추억'}],
      menuNo : 1,
      menuSlide: true
    }
  },
  methods: {
    menuChange : function(no) {
			this.menuNo = no
    },
    menuSlideSizing: function() {
      const obj = document.getElementById("slide-menu-bar")
      console.log('wlsdlq')
      if(this.menuSlide) {
				obj.style.width="10px"
      } else {
        obj.style.width="90%"
      }
			this.menuSlide = !this.menuSlide
    }
  },
  components: {
    Tab01, Tab02
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
