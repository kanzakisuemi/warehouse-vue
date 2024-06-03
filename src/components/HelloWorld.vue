<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/racoon_icon.png')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Galpões do Pedro
        </h1>

        <p class="subheadizng font-weight-regular">
          Essa é a aplicação de controle de galpões do Pedro, que pega dados de outro sistema.
          <br>O repositório da aplicação principal está disponível em:
          <a
            href="https://github.com/kanzakisuemi/warehouse-app"
            target="_blank"
          >Warehouse</a>
        </p>
      </v-col>

      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          Quer ver o repositório desse projeto?
        </h2>

        <v-row justify="center">
          <a
            href="https://github.com/kanzakisuemi/warehouse-vue"
            target="_blank"
          >Pedro Galpões</a>
        </v-row>
      </v-col>

    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      
    }),
  }
</script>
