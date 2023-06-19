<template>
    
    <div>
        <!-- 1) Exiba um alert quando o botÃ£o for clicado -->
    <div>
        <h2>1- Exiba um alert quando o botão for clicado</h2>
        <button v-on:click="alertClicado">Exibir Alerta</button>
    </div>
    
    <!-- 2) Escute o evento "keydown" e armazene o valor na propriedade
        data (dica: event.target.value) -->
    <div>
        <h2>2- Escute o evento "keydown" e armazene o valor na propriedade
        data</h2>
        <input type="text" v-on:keydown="alterarTitulo">
        <p>{{ valor }}</p>
    </div>
    
    <!-- 3) Ajuste o exemplo 2 para disparar o evento "keydown" somente
        quando a tecla for ENTER -->
    <div>
        <h2>3- Ajuste o exemplo 2 para disparar o evento "keydown" somente
        quando a tecla for ENTER</h2>
        <input type="text" v-on:keydown.enter="alterarTituloEnter">
        <p>{{ valor2 }}</p>
    </div>


    </div>

</template>

<script>

    export default {
        data(){
            return{
                valor: 'Alterar este valor',
                valor2: 'Alterar este valor'

            }

        },
        methods:{

            alertClicado(){
                alert('clicado')
            },
            alterarTitulo(e) {
                this.valor = e.target.value
            },
            alterarTituloEnter(e) {
                this.valor2 = e.target.value
            }
        }
    }
      

</script>

<style>

</style>