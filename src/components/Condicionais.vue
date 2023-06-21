<template>

    <div>
        <div v-if="logado">
            <p> Usuario Logado: {{ nome }} </p>
            <p>Perfil: admin</p>
        </div>
        <p v-else-if="anonimo"> Navegando anonimo</p>
        <p v-else> Nenhum usuario logado</p>
        <button @click="logado = !logado">{{ logado ? 'Sair' : 'Entrar' }}</button>
        <p><input type="checkbox" v-model="anonimo">anonimo?</p>
    </div>

</template>

<script>
    export default {
        data(){
            return{
                nome: 'Maria',
                logado: false,
                anonimo: true,




            }

        },
        computed:{

        },
        methods:{

        }
    }

</script>

<style>

</style>