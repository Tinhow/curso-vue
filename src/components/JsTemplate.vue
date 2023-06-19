<template>

    <div>
        <h2>{{ contador }}</h2>
        <button v-on:click="somar">somar</button>
        <p>{{ contador > 10 ? 'maior que 10' : 'menor que 10' }}</p>
    </div>

</template>

<script>
    export default {
        data(){
            return{
                contador: 0,

            }

        },
        methods:{
            somar(){
                this.contador ++
            }
        }
    }

</script>

<style>

</style>