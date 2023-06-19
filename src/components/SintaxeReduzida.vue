<template>
    <div>
        <h2> contador: {{ contador }}</h2>
        <button @click="somar">somar 1</button> <!-- @click é uma sintaxe reduzida para v-on:click -->
        <input type="text" :value="contador"> <!-- :value é uma sintaxe reduzida para v-bind:value -->
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

<style></style>