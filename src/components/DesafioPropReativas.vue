<template>

    <div>
        <!-- 1) Exibir em "resultado" o texto 'Valor Diferente' enquanto
        "valor" for diferente de 37 - "valor" ÃŠ alterado pelos botÃĩes.
        Mostrar 'Valor Igual' quando "valor" for igual a 37 -->

        <div>
            <h2>1- Exibir em "resultado" o texto 'Valor Diferente' enquanto
        "valor" for diferente de 37.
        Mostrar 'Valor Igual' quando "valor" for igual a 37</h2>
        
        <h2>{{ resultado }}: {{ valor }}</h2>
        <button @click="valor += 5">Somar 5</button>
        <button @click="valor += 1">Somar</button>
        

        </div>
            
        <!-- 2) Monitorar as mudanÃ§a de "resultado" e reiniciar "valor"
            para 0 depois de 5 segundos (dica: setTimeout(..., 5000) -->            
        <div>
            <h2>2- Monitorar as mudanças de "resultado" e reiniciar "valor"
            para 0 depois de 5 segundos (dica: setTimeout(..., 5000)</h2>

            <p>Valor atual: {{ valor }}</p>
            <button @click="valor += 5">Somar 5</button>
            <button @click="valor += 1">Somar 1</button>
            <p>{{ resultado }}</p>
        </div>

    </div>


</template>

<script>

    export default {
        data(){
            return{
                valor: 0

            }

        },
        computed:{
            resultado(){
                return this.valor == 37 ? 'Valor Igual' : 'Valor Diferente'
            }
        },
        watch:{
            resultado(){
                setTimeout(() => {
                    this.valor = 0
                }, 5000)
            }
        },
        methods:{
           
        }
    }

</script>

<style> 


</style>