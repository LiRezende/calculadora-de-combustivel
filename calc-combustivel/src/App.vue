<template>
  <v-app>
    <v-main>
      <InputGas/>
    </v-main>
  </v-app>
</template>

<script>
import InputGas from './components/InputGas';

export default {
  name: 'App',

  components: {
    InputGas,
  },

  data: () => ({
    //
  }),
};
</script>
