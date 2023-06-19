<template>
    <div>
        <h2>contador: {{ contador }} | {{ contador2 }}</h2>
        <h2> resultado: {{ resultado }}</h2>
        <button v-on:click="aumentar">aumentar</button>
        <button v-on:click="aumentar2">aumentar2</button>
        <button v-on:click="diminuir">diminuir</button>
    </div>

</template>

<script>
    export default {
        data(){
            return{
                contador: 0,
                contador2: 0,
            }

        },
        computed:{
            resultado(){
                console.log('chamando computed')
                return this.contador >= 5 ? 'maior ou igual a 5' : 'menor que 5' //não é necessario chamar como metodo
            } // uma propriedade computada é chamada apenas quando o valor é alterado
        },
        watch:{
            contador(novo, antigo){
                console.log(novo, antigo)
                setTimeout(() => {
                    this.contador = 0
                }, 10000)
                
            } //watch monitora uma propriedade e executa uma ação quando ela é alterada
        },
        methods:{
           aumentar(){
               this.contador ++
           },
           aumentar2(){
               this.contador2 ++
           },
           diminuir(){
               this.contador --
            } //,
        //    resultado(){
        //     console.log('chamando metodo')
        //        return this.contador >= 5 ? 'maior ou igual a 5' : 'menor que 5'
        //    } nesse modo o metodo era chamado mesmo que o valor não fosse alterado
        }
    }

</script>