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
    <hr>
    <footer v-show="logado">
        desenvolvido por: {{ nomeAutor }}
    </footer>
    <footer v-show="anonimo">
        desenvolvido para voce anonimo 👀
    </footer>

</template>

<script>
    export default {
        data(){
            return{
                nome: 'Maria',
                logado: false,
                anonimo: true,
                nomeAutor: 'Walter'




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