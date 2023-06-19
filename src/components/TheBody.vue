<template>
   <div>
        <h1>{{ body }}</h1>

        
   <div id="app" v-on:input="alterarTitulo"> <!--usando v-on // pega o que esta sendo escrito no input e põe no body-->
        <input type="text">
   </div>

   <a v-bind:href="link">vai para o gooogle? usando v-bind </a> <!--usando v-bind // pega o link que esta dentro da variavel "link" -->
   <p v-html="htmlLink"></p> <!--usando v-html // pega o html que esta dentro da variavel "htmlLink"-->

   </div> 


</template>


<script>

export default {
  data() {
    return { //onde são adicionados os dados/variaveis
      body: 'body',
      link: 'https://www.google.com',
      htmlLink: '<a href="https://www.google.com">vai para o google? usando v-html</a>',
    };
  },
  methods: { //onde são adicionados os metodos
    alterarTitulo(e) {
      this.body = e.target.value; //altera o valor da variavel "body" para o que esta sendo escrito no input
    },
  },
};




</script>



<style>

</style>