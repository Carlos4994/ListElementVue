<template>
    <div>
        <div class="box" v-for="e in elements" v-bind:key="e">
           {{ e }}
        </div>
        <button v-on:click="findAll">Consola</button>
        {{ msj }}
    </div>
</template>


<script>
export default {
    data(){
        return{
            msj:"... :(",
            elements: ["uno","dos","tres"]
        }
    },

    methods: {
        findAll: function () {
           fetch('http://localhost:8000/api/type/?format=json').then(res=> res.json()).then(res => console.log(res))
        }
        
    },
}
</script>

<style>
.box{
    font-family: 'Courier New', Courier, monospace;
    font-size: medium;
}
</style>