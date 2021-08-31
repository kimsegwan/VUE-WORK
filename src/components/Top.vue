<template>
    <div class="top-menu-list">
		<ul class="top-menu-box">
			<li v-for="menu in menuList" :key="menu.no">
                {{menu.name}}
            </li>
        </ul>
    </div>
</template>

<script>

export default({
    name: 'Top',
    data() {
        return {
            menuList: [{no: 1, name: '소개'},
            			{no: 2, name: '여행지'},
                        {no: 3, name: '음식점'},
                        {no: 4, name: '계획'}]
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
</style>
