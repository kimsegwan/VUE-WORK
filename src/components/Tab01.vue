<template>
    <div class="contents-tab01">
        <div class="main-body">
            <div class="main-body-menu" v-for="menu in menuList" :key="menu.no">
                <h1>{{menu.name}}</h1>
            </div>
        </div>
        <div class="contents-img-box">
            <div>
                <img :src="require(`@/assets/logo.png`)" />
            </div>
            <div></div>
        </div>

        <button @click="getData">데이터 수신</button>
        <div>
            <table>
                <tr v-for="(val, idx) in result" :key="idx">
                    <td>{{ idx }}</td>
                    <td>{{ val }}</td>
                </tr>
            </table>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

export default ({
    name: 'Tab01',
    data() {
        return {
            menuList : [
                {id: 0, name: '메뉴1'},
                {id: 1, name: '메뉴2'},
                {id: 2, name: '메뉴3'},
                {id: 3, name: '메뉴4'},
                ],
            result: null,
            show: true,
            text: ''
        }
    },
    methods: {
        gogo: function() {
            //alert(this.$parent.rootDataMain)
            this.show = !this.show
        },
        getData: function() {
            axios.get('https://raw.githubusercontent.com/joshua1988/doit-vuejs/master/data/demo.json')
							.then((response) => {
                                console.log(response)
								this.result = response.data
							}).catch(error => {
                                alert(error)
                            })
        }
    }
})
</script>

<style scope>
.contents-tab01 {
    width: 100%;
}

.contents-html-box {
    background-color: white;
    height:300px;
    width:250px;
    margin: 0px auto;
}

.contents-img-box img {
    width:150px;
    height: 150px;
}

.main-body {
    width: 98%;
    margin: 0 auto;
    overflow:hidden;
}

.main-body-menu {
    max-width: 540px;
    width: 45%;
    height: 300px;
    background-color: #999;
    border-radius: 10px;
    margin: 15px;
    float: left;
}

@media screen and (max-width: 680px) {
    .main-body {
        margin: 15px auto;
    }

    .main-body-menu {
        width:90%;
        max-width: 440px;
        margin: 15px auto;
        float: initial;
    }
}

</style>