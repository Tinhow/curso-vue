<template>
    <h1>listas-condicionais</h1>
    
    <div>
        <h2>Lista Cores</h2>
        <ul>
            <li v-for="(cor, i) in cores" :key="i"> {{ i }}) - {{ cor }} </li>
        </ul>
        <input type="text" v-model="cor">
        <button @click="adicionar">adicionar</button>
    </div>
    <div>
        <h2>Lista nomes</h2>
        <ul>
            <li v-for="(pessoa, i) in pessoas" :key="i"> {{ i }}) - {{ pessoa.nome }} </li>
        </ul>
    </div>

    <div>
        <li v-for="pessoa in pessoas" :key="pessoa">
            <div v-for="(valor, chave) in pessoa" :key="valor">
                {{ chave }} = {{ valor }}
            </div>
        </li>
        <br>
        <div class="n" v-for="(n , i) in 10" :key="n">
            (indice = {{ i }} | numero = {{ n  }} )
        </div>
    </div>
         
</template>

<script>
    export default {
        data(){
            return{
                    cores: ['vermelho', 'verde', 'azul', 'amarelo'],
                    pessoas: [
                        {nome: 'Maria', idade: 34, peso: 64},
                        {nome: 'Joao', idade: 67, peso: 78},
                      
                    ]

            }

      
        },
        methods:{
            adicionar(){
                this.cores.push(this.cor)
            }

        }
    }

</script>

<style>
    li{
        list-style: none;
    }

    

</style>