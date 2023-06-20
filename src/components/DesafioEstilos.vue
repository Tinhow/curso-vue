<template>
    <div>
        <h1>Desafio Estilos Dinamicos</h1>
        <!-- 1) Iniciar a execuçao do efeito usando botao. 
        O efeito deve alternadamente trocar as classes "destaque" e
        "encolher" para cada chamada de setInteval. Use a div abaixo
        com id "efeito" para associar as classes CSS. -->
        <h2>#01 Iniciar a execuÃ§Ã£o do efeito usando botÃ£o. 
        O efeito deve alternadamente trocar as classes "destaque" e
        "encolher" para cada chamada de setInteval. Use a div abaixo
        com id "efeito" para associar as classes CSS.</h2>
      
        <div>
            <button @click="iniciarEfeito">Iniciar Efeito</button>
            <div id="efeito"></div>
        </div>
        
        <!-- 2) Crie duas classes CSS e associe a div usando a
            sintaxe de array -->
        <h2>#02</h2>
        <div >Estou sem classe CSS :(</div>

        <!-- 3) Aplique na div abaixo a classe informada pelo usuÃ¡rio
            (crie classe CSS de exemplo). -->
        <h2>#03</h2>
        <div>
            <input type="text">
            <div></div>
        </div>

        <!-- 4) Aplique na div abaixo a classe informada pelo usuÃ¡rio e
        outra classe usando o valor true/false (crie classes CSS de exemplo). -->
        <h2>#04</h2>
        <div>
            <input type="text">
            <input type="text">
            <div></div>
        </div>

        <!-- 5) Repita 3) mas utilizando estilos ao invÃ©s de classes CSS.
        Associe os estilos a div abaixo  -->
        <h2>#05</h2>
        <div>
            <input type="text">
            <div></div>
        </div>

        <!-- 6) Crie uma barra de progresso simples com setInterval 
        e binding de estilo. -->
        <h2>#06</h2>
        <div>
            <button @click="iniciarProgresso">Iniciar</button>
            <div></div>
        </div>

    </div>
</template>

<script>
    export default {
        data(){
            return{

            }

        },
        methods:{
            estilo1(){
                return{
                    c1: this.aplicarC1,
                    c2: !this.aplicarC1
                },
            iniciarEfeito(){

            },
            iniciarProgresso(){

            }

        }
    }
</script>

<style>

#efeito {
	width: 100px;
	height: 100px;
	border: 1px solid black;
    margin:auto;
}

.destaque {
	background-color: red;
	width: 200px !important;
}

.encolher {
	background-color: gray;
	width: 50px !important;
}

</style>