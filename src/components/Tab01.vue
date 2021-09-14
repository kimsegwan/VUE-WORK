<template>
    <div class="contents-tab01">
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

<style>
.contents-tab01 {
    padding: 10px;
    width: 100%;
}

.contents-html-box {
    background-color: white;
    height:300px;
    width:250px;
    margin: 0px auto;
}

.contents-img-box {
    
}

.contents-img-box img {
    width:150px;
    height: 150px;
}
</style>