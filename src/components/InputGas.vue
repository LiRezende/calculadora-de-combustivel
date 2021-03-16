<template>
  <div class="input-gas">
    <h2>Calculadora de Combustível</h2>
    <h3>
      Insira os valores do Etanol e Gasolina, para calcular qual é mais vantajoso.
    </h3>
    <form>
      <v-text-field
        v-model.number="valueAlcohol"
        label="Valor do Etanol"
      ></v-text-field>
      <v-text-field
        v-model.number="valueGas"
        label="Valor da Gasolina"
      ></v-text-field>
    </form>
    <v-dialog v-model="dialog" width="500">
      <template v-slot:activator="{ on, attrs }">
        <v-btn v-bind="attrs" v-on="on" @click="calcDifer"> calcular </v-btn>
      </template>

      <v-card>
        <v-card-title color="#000">
          <h3>A diferença é {{ (diference).toFixed(2) }}</h3>
        </v-card-title>
        <v-card-text>
          <p v-if="diference > 0.7">Abasteça com GASOLINA!</p>
          <p v-else-if="diference < 0.7">Abasteça com ÁLCOOL / ETANOL!</p>
          <p v-else>Nesse caso, não faz diferença. A escolha é sua!</p>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" text @click="dialog = false"> fechar </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-footer class="transparent">
      <v-col class="text-center" cols="12">
        <a href="https://github.com/LiRezende">
          {{ new Date().getFullYear() }} © Desenvolvido por Ligia Brusamolin de Rezende
          <v-icon color="#26A69A">mdi-github</v-icon>
        </a>
        <a href="https://github.com/LiRezende">
          <v-icon color="#26A69A">mdi-linkedin</v-icon>
        </a>
      </v-col>
    </v-footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
        diference: 0,
        dialog: false,
    };
  },
  methods: {
    calcDifer() {
      this.diference = this.valueGas / this.valueAlcohol;
    },
  },
};
</script>

<style scoped>
div {
  margin-top: 30px;
}
h3 {
  font-weight: 400;
}
p {
  font-size: 18px;
  text-align: center;
}
a {
  color:#26A69A!important;
  text-decoration: none;
}
.input-gas {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
form, footer {
  padding-top: 20px;
}
</style>