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
.top-menu-list {
	margin-top: 15px;
    overflow: hidden;
}

.top-menu-box {
	overflow: hidden;
    float: right;
    border-bottom: 1px solid black;
    opacity: .8;
}

.top-menu-box li {
    list-style: none;
	float: left;
    width: 70px;
    padding: 5px 0px;
    cursor: pointer;
    font-weight: bold;
}

.top-menu-box li:hover {
    /* background-color: rgb(236, 241, 227); */
    border-radius: 5px;
    line-height: 18px;
}

.top-menu-box li:last-child {
    margin-right: 10px;
}
</style>
