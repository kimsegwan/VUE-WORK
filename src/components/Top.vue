<template>
    <div class="top-menu-list">
		<!-- <ul class="top-menu-box">
			<li v-for="menu in menuList" :key="menu.no" @click="menuAlt(menu.name)">
                {{menu.name}}
            </li>
        </ul> -->
        <div class="top-menu-box">
            <router-link :to="menu.link" v-for="menu in menuList" :key="menu.no" class="top-menu" @click="menuAlt(menu.name)">
                {{menu.name}}
            </router-link>
        </div>
    </div>
</template>

<script>

export default({
    name: 'Top',
    props : ['propsdata'],
    data() {
        return {
            menuList: [{no: 1, name: '소개', link: '/'},
            			{no: 2, name: '여행지', link: '/menu02'},
                        {no: 3, name: '음식점', link: '/menu03'},
                        {no: 4, name: '계획', link: '/menu04'}]
        }
    },
    methods : {
        menuAlt : function(text) {
            this.$emit('menuText', text)
        }
    }
})
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nanum+Myeongjo:wght@400;700;800&display=swap');

@font-face {
    font-family: 'GowunDodum-Regular';
    src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2108@1.1/GowunDodum-Regular.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}                                                                                                                                                                                                                                                                                

.top-menu-list {
	margin-top: 15px;
    overflow: hidden;
}

.top-menu-box {
	overflow: hidden;
    float: right;
    border-bottom: 1px solid #444;
    opacity: .8;
}

.top-menu-box li {
    list-style: none;
	float: left;
    width: 70px;
    padding: 5px 0px;
    cursor: pointer;
    font-weight: bold;
    font-family: 'Nanum Myeongjo', serif;
}

.top-menu-box li:hover {
    border-radius: 5px;
    line-height: 12px;
}

.top-menu-box li:last-child {
    margin-right: 10px;
}

.top-menu {
    padding: 15px;
    text-decoration: none;
	float: left;
    width: 70px;
    padding: 5px 0px;
    cursor: pointer;
    font-weight: bold;
    font-family: 'Nanum Myeongjo', serif;
    color: #333;
}

.top-menu:hover {
    border-radius: 5px;
    line-height: 12px;
}
</style>
