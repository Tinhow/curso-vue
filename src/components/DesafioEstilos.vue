<template>
    <div>
        <h1>Desafio Estilos Dinamicos</h1>
        <!-- 1) Iniciar a execuçao do efeito usando botao. 
        O efeito deve alternadamente trocar as classes "destaque" e
        "encolher" para cada chamada de setInteval. Use a div abaixo
        com id "efeito" para associar as classes CSS. -->
        <h2></h2>
      
        <div>
            <button @click="iniciarEfeito">Iniciar Efeito</button>
            <div id="efeito" :class="classe1"></div>
        </div>
        
        <!-- 2) Crie duas classes CSS e associe a div usando a
            sintaxe de array -->
        <h2>#02</h2>
        <div :class="[{teste}, 'teste1']">Estou sem classe CSS :</div>

        <!-- 3) Aplique na div abaixo a classe informada pelo usuÃ¡rio
            (crie classe CSS de exemplo). -->
        <h2>#03</h2>
        <div>
            <div class="demo" :class="demo">
            </div>
            <br>
            <input type="text" v-model="demo">

        </div>

        <!-- 4) Aplique na div abaixo a classe informada pelo usuÃ¡rio e
        outra classe usando o valor true/false (crie classes CSS de exemplo). -->
        <h2>#04</h2>
        
        <div>
            <div :class="[classe3, {perigo}]"></div>
            <br>
            <input type="text" v-model="classe3">
            <br>
            <input type="text" @input="setPerigo">
        </div>

        <!-- 5) Repita 3) mas utilizando estilos ao invÃ©s de classes CSS.
        Associe os estilos a div abaixo  -->
        <h2>#05</h2>
        <div>
            <input type="text" v-model="cor1">
            <div :style="[estilo2, {backgroundColor: cor1}]"></div>
        </div>

        <!-- 6) Crie uma barra de progresso simples com setInterval 
        e binding de estilo. -->
        <h2>#06</h2>
        <div>
            <button @click="iniciarProgresso">Iniciar</button>
            <div class="barra-progresso">
                <div class="progresso" :style="{width}"></div>
            </div>
        </div>
        <br>

    </div>
</template>

<script>
    export default {
        data(){
            return{
                demo: '',
                addEstilo: 'c1',
                classe1: 'destaque',
                classe2: 'encolher',
                teste: true, //se o nome da classe for igual ao valor da variavel, ela é aplicada usando apenas uma vez
                classe3: '',
                classe4: '',
                perigo: true,
                cor1: '',
                estilo2: {
                    width: '100px',
                    height: '100px',
                    backgroundColor: 'green',
                    margin: 'auto'
                },
              width: '0'
            }
           
        },
        methods:{
            estilo1(){
                return{
                    c1: this.aplicarC1,
                    c2: !this.aplicarC1
                }
            },

            iniciarEfeito(){
                {
                setInterval(() => {
                    this.classe1 = this.classe1 == 'destaque' ? 'encolher' : 'destaque'
                }, 1000);
            }   

            },
            iniciarProgresso(){
                let valor = 0
                 setInterval(() => {
                    valor += 5
                    this.width = `${valor}%`
                    if(valor == 100){ 
                        valor = 0
                    }
                }, 500);

            },
            setPerigo(event){
                if(event.target.value == 'true'){
                    this.perigo = true
                }else if(event.target.value == 'false'){
                    this.perigo = false
                }
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
	background-color: blue;
	width: 200px !important;
}

.demo{
    width: 100px;
    height: 100px;
    background-color: gray;
    margin: auto;
}

.c1{
    background-color: red;
    width: 100px;
    height: 100px;
    margin: auto;
}

.c2{
    background-color: blue;
    width: 100px;
    height: 100px;
    margin: auto;
}

.c3{
    background-color: green;
    width: 100px;
    height: 100px;
    margin: auto;
}

.teste{
    background-color: black;
}

.teste1{
    width: 100px;
    height: 100px;
    margin: auto;
}

.direita{
    float: right;
}

.perigo{
    background-color: red;
  
}

.quadrado{
    width: 100px;
    height: 100px;
    margin: auto;
}

.barra-progresso{
    width: 200px;
    height: 30px;
    margin: auto;
    border: 1px solid black;
}

.progresso{
    width: 10px;
    height: 100%;
    background-color: green;}

</style>