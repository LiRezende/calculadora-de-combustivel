<template>
<div class="input-gas">
    <h2>Calculadora de Combustível</h2>
    <h3>Insira os valores do Etanol e Gasolina, para calcular qual é mais vantajoso.</h3>
    <form>
        <v-text-field
          v-model="valueAlcohol"
          :error-messages="errors"
          label="Valor do Alcool"
          required
        ></v-text-field>
        <v-text-field
          v-model="valueGas"
          :error-messages="errors"
          label="Valor da Gasolina"
          required
        ></v-text-field>
    </form>
    <button @click="calcularDifer">Calcular</button>
    <p>{{ diferenca }}</p>
</div>

</template>

<script>
export default {
    data () {
        return {
            diferenca: 0
        }
    },
    methods: {
      calcularDifer () { 
          this.diferenca = this.valueGas / this.valueAlcohol;
      }
    },
}    
</script>

<style scoped>
    h2, h3 {
        font-weight: 300;
    }
    h2 {
        margin-top: 20px;
    }
    .input-gas {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }
    form {
        padding-top: 20px;
    }
</style>