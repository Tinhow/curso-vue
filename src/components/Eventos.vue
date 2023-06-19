<template>
    <div>
        <h1>{{ eventos }}</h1>
        <p>{{ contador }}</p>
        <button v-on:click="somar(1)">somar 1</button>
        <br>
        <div class="areaXY">
         <h1  v-on:mousemove="moveXY">mouse {{ x }} e {{ y }}
          <p v-on:mousemove.stop="">aqui não pega</p>
        </h1>
        </div>
        <a v-on:click="naoNavegar" href="http:gooogle.com">gooogle? prevenção de evento</a>
        <br>
        <h1>Pegar evento - Enter</h1>
        <input type="text"  v-on:keyup.enter="exibirAlerta">
        <br>
        <h1>Pegar evento - qualquer tecla</h1>
        <input type="text"  v-on:keyup="exibirAlertaQualquerTecla">

    </div>
</template>

<script>

    export default {
      data() {
        return { 
            eventos: 'eventos',
            contador: 0,
            x: 0,
            y: 0,
        };
      },
      methods: { 
        somar(soma){
          this.contador += soma
        },
        moveXY(e){
          console.log(e)
          this.x = e.clientX
          this.y = e.clientY
        },
        naoNavegar(e){
          e.preventDefault() // não deixa um evento padrão acontecer
          alert('Não vai navegar')
        },
        exibirAlerta(){
          alert('voce apertou enter') // modificador de acesso da tecla enter
        },
        // parar(e){
        //   e.stopPropagation() // não deixa um evento padrão acontecer
        // }
        exibirAlertaQualquerTecla(){
          alert('voce apertou qualquer tecla') // pega o acesso de qualquer tecla
        },
      } 
    }
    

</script>

<style>

  .areaXY{
    background-color: #000;
    color: #fff;
    padding: 20px;
    text-align: center;
    width: 400px;
    margin:auto;
    margin-top: 5%;
  }

</style>