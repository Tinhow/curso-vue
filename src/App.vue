<template>
  <div>
    <TheHeader />
    <img v-show="showImg" alt="Vue logo" src="./assets/logo.png">
    <div>
      Nome: {{ name }}
    </div>
    <div v-if="accessLevel === 'admin'">usuario administrador</div>
    <div v-else-if="accessLevel === 'normal'">usuario normal</div>
    <div v-else> usuariario não encontrado</div>
    <br>
    <div v-for="obj in todos" v-bind:key="obj.id">
      {{ obj.title }}
    </div>
    <hr>
    <the-body />
    <hr>
    <eventos />
    <hr>
    <!-- <desafio-teste /> -->
    <!--<desafio-eventos />-->
    <js-template />
    <hr>
    <two-way />
    <hr>
    <propiedades-reativas />
    <hr>
    <sintaxe-reduzida />
    <hr>
    <!--<desafio-propriedades-reativas />-->
    <estilos-dinamicos />
    <hr>
    <!--<desafio-estilos /> -->
    <condicionais />
    <hr>
    <listas-condicionais />
    <hr>
    <!--<desafio-condicionais />-->
    <projeto-jogo-monstro />
    
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import TheBody from './components/TheBody.vue';
import Eventos from './components/Eventos.vue';
//import DesafioTeste from './components/DesafioTeste.vue';
//import DesafioEventos from './components/DesafioEventos.vue';
import JsTemplate from './components/JsTemplate.vue';
import TwoWay from './components/TwoWay.vue';
import PropiedadesReativas from './components/PropiedadesReativas.vue';
import SintaxeReduzida from './components/SintaxeReduzida.vue';
//import DesafioPropriedadesReativas from './components/DesafioPropReativas.vue';
import EstilosDinamicos from './components/EstilosDinamicos.vue';
//import DesafioEstilos from './components/DesafioEstilos.vue';
import Condicionais from './components/Condicionais.vue';
import ListasCondicionais from './components/ListasCondicionais.vue';
//import DesafioCondicionais from './components/DesafioCondicionais.vue';
import ProjetoJogoMonstro from './components/ProjetoJogoMonstro.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheBody,
    Eventos,
    //Desafio2Teste,
    //Desafio1Eventos
    JsTemplate,
    TwoWay,
    PropiedadesReativas,
    SintaxeReduzida,
    //DesafioPropriedadesReativas
    EstilosDinamicos,
    //DesafioEstilos
    Condicionais,
    ListasCondicionais,
    //DesafioCondicionais,
    ProjetoJogoMonstro
    

    
  },
  data() {
    return {
      showImg: true,
      name: 'Vue',
      accessLevel: 'admin',
      todos:[ 
      {
        "userId": 1,
        "id": 1,
        "title": "delectus aut autem",
        "completed": false
      },
      {
        "userId": 1,
        "id": 2,
        "title": "quis ut nam facilis et officia qui",
        "completed": false
      },
      {
        "userId": 1,
        "id": 3,
        "title": "fugiat veniam minus",
        "completed": false
      },
      {
        "userId": 1,
        "id": 4,
        "title": "et porro tempora",
        "completed": true
      },
      {
        "userId": 1,
        "id": 5,
        "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
        "completed": false
      }   
        
    ]
      
    }
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
