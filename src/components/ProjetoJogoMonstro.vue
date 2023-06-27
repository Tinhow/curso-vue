<template>

    <div class="templateGeral"> 
      
        <div class="painel scores">
             
            <div class="score">
                <h1>Jogador</h1>
                <div class="life-bar">
                    <div class="life"
                    :class="{danger: playerLife < 20 }"
                    :style="{width: playerLife + '%'}"></div>
                </div>
                <div>{{ playerLife }}%</div>
            </div>

            <div class="score">
                <h1>Monstro</h1>
                <div class="life-bar">
                    <div class="life"
                    :class="{danger: monsterLife < 20 }"
                    :style="{width: monsterLife + '%'}"></div>
                </div>
                <div>{{ monsterLife }}%</div>
            </div>
        </div>


        <div v-if="hasResult" class="painel results">
            <div v-if="monsterLife == 0" class="win"> Voce ganhou !!!</div>
            <div v-else class="lose"> Voce perdeu !!!</div>

        </div>

        <div class="painel buttons">
            <div v-if="!running">
                <button @click="startGame" class="btn start">Iniciar Jogo</button>
            </div>
            <div v-else>
                <button @click="atk(false)" class="btn atk">Ataque</button>    
                <button @click="atk(true)" class="btn atkEsp">Especial</button>
                <button @click="heal" class="btn heal">Curar</button>
                <button @click="stopGame" class="btn giveUp">Desistir</button>
            </div>
        </div>

        <div class="painel logs">


        </div>
        

      


    </div>
   

</template>

<script>
    export default {
        data(){
            return{
                running: false,
                playerLife: 80,
                monsterLife: 100,

            }

        },
        methods:{
            startGame(){
                this.running = true
                this.playerLife = 100,
                this.monsterLife = 100
            },
            stopGame(){
                this.running = false
            },
            atk(especial){
                this.hurt('playerLife', 7, 12, false)  
                this.hurt('monsterLife', 5, 10, true)  
                console.log(especial)

            },
            heal(){
                this.playerLife = Math.min(this.playerLife + 10, 100)
            },
            getRandom(min, max){
                const value = Math.random() * (max - min) + min
                return Math.round(value)
            },
            hurt(atr, min, max, especial){
                const plus = especial ? 5 : 0
                const hurt = this.getRandom(min + plus, max + plus)
                this[atr] = Math.max(this[atr] - hurt, 0)
            }

        },
        computed:{
            hasResult(){
                return this.playerLife == 0 || this.monsterLife == 0
            }

        },
        watch:{
            hasResult(value){
                if(value) this.running = false
            }

        }

    }   
</script>

<style>
    .templateGeral{
        font-family: 'Montserrat', sans-serif;
        display: flex;
        flex-direction: column;
    }

    .painel{
        margin: 10px;
        padding: 20px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.20);
        background-color: rgba(67, 74, 196, 0.705);
    }

   .scores{
        display: flex;
   }

   .score{
        flex: 1;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
   }
    
   .score h1{
        font-weight: 300;
        font-size: 1.6rem;
        color: black;
   }

    .life-bar{
          width: 80%;
          height: 20px;
          background-color: white;
          border-radius: 5px;
          border: 1px solid rgb(184, 147, 147);
          display: flex;
        }
    
    .life-bar .life{
        display: flex;
        justify-content: center;
        height: 100%;
        background-color: green;

    }
       
    .life-bar .life.danger{
        background-color: red;
    }
    
    .win{
        font-size: 2rem;
        color: green;
        font-weight: 300;
    }

    .lose{
        font-size: 2rem;
        color: red;
        font-weight: 300;
    }

    .buttons{
        display: flex;
        justify-content: space-around;

    }


    .btn{
        padding: 5px 10px;
        margin: 0px 10px;
        border-radius: 5px;
        text-transform: uppercase;
        font-size: 1.1rem;
        
       
    }

    .start{
        background-color: rgb(0, 0, 0);
        color: white;
    }


    .atk{
        background-color: red;
        color: white;
    }

    .atkEsp{
        background-color: orangered;
        color: white;

    }

    .heal{
        background-color: green;
        color: white;

    }

    .giveUp{
        background-color: black;
        color: white;

    }

    .telaResultados{
        display: flex;
        justify-content: space-around;
        border: 2px solid black;
        margin-top: 5%;

    }

</style>