<template>
   
   <div>
        <h1>Estilos Dinamicos</h1>
        <div id='div1'>
            <div class="caixas">
                <div class="demo"  :class="estilo1"  @click="aplicarC1 = !aplicarC1"></div> <!-- estilo1 foi utilizado para aplicar a classe c1 -->
                <div class="demo" :class="{c2: aplicarC2}" @click="aplicarC2 = !aplicarC2"></div> <!-- :class="{c2: aplicarC2}" foi utilizado para aplicar a classe c2 -->   
                <div class="demo" :class="[classeCSS, {girar: aplicarGirar} ]" ></div> <!-- Two-Way data Binding para alterar a classeCSS -->
            </div>
            <br>
            <h2>escolha entre c1, c2 e c3 para aplicar uma classe no ultimo quadrado</h2>
            <input type="text" v-model="classeCSS"> <!-- :class="[classeCSS]" foi utilizado para aplicar a classe c3 --> 
            <hr>
            <div class="caixas">
                <div class="demo" :style="{'backgroundColor': cor}"></div> 
                <div class="demo" :style="[meuEstilo, {height: altura}]"></div>   
                <div class="demo" :style="[meuEstilo]"></div> 
            </div>
            <br>
            <input type="text" v-model="cor">
            <input type="text" v-model="largura">
            <input type="text" v-model="altura">
        </div>
    </div>


</template>

<script>
    export default {
        data(){
            return{

                aplicarC1: false,
                aplicarC2: false,
                aplicarC3: false,
                classeCSS: 'c3',
                aplicarGirar: true,
                cor: 'red',
                largura: 100,
                altura: 20 ,

            }

        },
        computed:{
            estilo1(){
                return{
                    c1: this.aplicarC1,
                    c2: !this.aplicarC1,
                }
            },
            meuEstilo(){
                return{
                    backgroundColor: this.cor,
                    width: this.largura + 'px',
                    height: this.altura + 'px',
                }
            }
        },
        methods:{

        }
    }

</script>

<style>

    .caixas{
        display: flex;
        justify-content: space-around;
    }

    .demo{
        width: 100px;
        height: 100px;
        background-color: gray;
    }

    .c1{
        background-color: red;
    }

    .c2{
        background-color: blue;
    }

    .c3{
        background-color: green;
    }

    .girar{
        transform: rotate(45deg);
    }

</style>