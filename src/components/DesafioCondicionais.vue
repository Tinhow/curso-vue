<template>
    <h1>Desafio condicionais</h1>
    <div>
         <!-- 1) Ligue o botão para alternar a exibição dos dois
    parágrafos. Use ambos v-if e v-show e inspecione os elementos
    para ver a diferença -->
  <h2>#01</h2>
  <div>
    <button @click="alternar = !alternar">Alternar</button>
    <p v-if="alternar">Você quer me ver (v-if)...</p>
    <p v-else>...ou eu (v-if)</p>
    <p v-show="alternar">Você quer me ver (v-show)...</p>
    <p v-show="!alternar">...ou eu (v-show)</p>
  </div>

  <!-- 2) Exiba em uma <ul> um array de elementos da sua escolha.
    Imprima também o índice de cada elemento. -->
  <h2>#02</h2>
  <ul>
    <li v-for="(pessoa, i) in pessoas" :key="i">
       {{ i }}) {{ pessoa }} </li>
  </ul>
  
  <!-- 3) Imprimir todos os pares de valor-chave do objeto a seguir:
    {
			titulo: 'O Senhor dos Anéis',
			autor: 'J.R.R. Tolkiens',
			volume: '3'
		}
    Imprima também o índice de cada item. -->
  <h2>#03</h2>
  <ul>
    <li v-for="(livro, chave, i) in livros" :key="i">
        {{i}} - {{ chave }} - {{ livro }}
    </li>
  </ul>
  
  <!-- 4) Imprima o seguinte objeto (somente os valores) e
    também crie um loop aninhado para o array:
    {
			id: 10,
			nome: 'Maria',
			notas: [7.67, 8.33, 6.98, 9.21]
		}
    (dica: use v-for e v-if na resolução) -->
  <h2>#04</h2>
  <ul>
    <li v-for="a in alunos" :key="a">
        <template v-if="!Array.isArray(a)">
            {{ a }}
        </template>
        <template v-else>
            notas:
            <ul>
                <li v-for="nota in a" :key="nota"> {{ nota }}</li>
            </ul>
           
        </template>
    </li>
  </ul>


    </div>
</template>

<script>
    export default {
        data(){
            return{
                alternar: true,
                pessoas: [ 'Maria', 'Joao', 'Pedro', 'Ana', 'Bia', 'Carlos', 'Daniel'
                ],
                livros: {
                    titulo: 'O Senhor dos Anéis',
                    autor: 'J.R.R. Tolkiens',
                    volume: '3'
                },
                alunos: {
                    id: 10,
                    nome: 'Maria',
                    notas: [7.67, 8.33, 6.98, 9.21]
                }
            }

        },
        methods:{

        }
    }
</script>

<style> 

</style>