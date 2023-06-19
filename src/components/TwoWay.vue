<template>

    <div>
        <h1>{{ title }}</h1>
        <input type="text" v-model="title"> <!-- Two-Way data Binding -->   
    </div>
    <br>

</template>

<script>
    export default {
        data(){
            return{
                title: 'Two-Way data Binding',
            }

        },
        methods:{
            twoWay(e){
                this.title = e.target.value
            }

        }
    }

</script>

<style>

</style>