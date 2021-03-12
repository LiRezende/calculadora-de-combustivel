<template>
<div class="input-gas">
    <h2>Calculadora de Combustível</h2>
    <h3>Insira os valores do Etanol e Gasolina, para calcular qual é mais vantajoso.</h3>
    <form>
        <v-text-field
            label="Valor do Etanol"
            outlined
        ></v-text-field>
        <v-text-field
            label="Valor da Gasolina"
            outlined
        ></v-text-field>
         <v-btn
            class="mr-4"
            type="submit"
            :disabled="invalid"
        >
            enviar
        </v-btn>
        <v-btn @click="clear">
            limpar
        </v-btn>
    </form>
</div>

</template>

<script>
export default {
    
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