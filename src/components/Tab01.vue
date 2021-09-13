<template>
    <div class="contents-tab01">
        Tab01
        <br/>
        <br/>
        <br/>
        <br/>
        <h1>소개</h1>
        <button @click="getData">데이터 수신</button>
        <div>
            <table>
                <tr v-for="(val, idx) in result" :key="idx">
                    <td>{{ idx }}</td>
                    <td>{{ val }}</td>
                </tr>
            </table>
        </div>
        <button @click="gogo()">눌러봐</button>
        <transition name="fade" mode="out-in">
            <p v-if="show">HELLO</p>
        </transition>
    </div>
</template>

<script>
import axios from 'axios'

export default ({
    name: 'Tab01',
    data() {
        return {
            result: null,
            show: true
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
</style>