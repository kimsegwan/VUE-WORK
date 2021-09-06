<template>
    <div class="contents-tab01">
        Tab01
        <br/>
        <br/>
        <br/>
        <br/>
        <h1>소개</h1>
        <button @click="getData">데이터 수신</button>
        <br/>
        <span>{{ apiText }}</span>
    </div>
</template>

<script>
import axios from 'axios'

export default ({
    name: 'Tab01',
    data() {
        return {
            apiText: []
        }
    },
    methods: {
        getData: function() {
            axios.get('https://raw.githubusercontent.com/joshua1988/doit-vuejs/master/data/demo.json')
							.then(function(response) {
                                const text= response
                                console.log(text)
								this.apiText= text
							}).catch(error => {
                                alert(error)
                            })
        }
    }
})
</script>

<style>
.contents-tab01 {
    padding:10px;
    width: 100%;
    height: 1000px;
}
</style>