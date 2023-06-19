<template>
   <!--desafio feito com sucesso / tirei da renderização-->
   <div>
        <h1>{{ titulo }}</h1>      
    <div>
    <br>
        <!-- 1) Preencha a tag <p> abaixo com o seu Nome e Idade - usando Interpolação -->
       
        <p> 1)Preencha a tag p abaixo com o seu Nome e Idade - usando Interpolação</p>
        <p>Usando VueJS - {{ nome }}, {{ idade }} anos</p>
        <br>

        <!-- 2) Exiba sua idade multiplicada por 3 -->
        <p>2) Exiba sua idade multiplicada por 3</p>
        <p>{{ idade * 3 }} </p>
        <br>
        
        <!-- 3) Chame uma função para exibir um número randomico
            entre 0 and 1 (Math.random()) -->
        <p>3) Chame uma função para exibir um número randomico
            entre 0 and 1 </p>
        <p> {{ numeroRandomico() }} </p>
        <br>

        <!-- 4) Procure uma imagem no google e exiba na tag img 
            fazendo o binding no atributo "src" -->
        <p>4) Procure uma imagem no google e exiba na tag img 
            fazendo o binding no atributo "src"</p>
        <div>
            <img v-bind:src="linklImg" height="400">
        </div>
        
        <!-- 5) Inicialize o input com o seu nome (use o atributo "value") -->
        <p> 5) Inicialize o input com o seu nome </p>
        <div>
            <input type="text" v-bind:value="nome">
        </div>

    </div>
    </div>

  

</template>

<script>

    export default {
        data() {
            return {
                titulo: 'começando o desafio',
                nome: 'Walter Filho',
                idade: 22,
                linklImg: 'https://miro.medium.com/v2/resize:fit:918/1*s2vCxDgTCjVt8AyAyFIDhw.png'
            };
        },
        methods: {
            numeroRandomico() {
                return (Math.random(0,1))
            }
        }
    }
</script>

<style>

</style>