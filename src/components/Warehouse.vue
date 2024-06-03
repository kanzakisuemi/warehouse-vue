<template>
  <v-card class="card mx-auto">
    <v-card-item>
      <v-card-title>{{ name }} - {{ code }}</v-card-title>
      <v-card-subtitle>{{ city }}</v-card-subtitle>
    </v-card-item>
    <v-card-text>Endereço: {{ address }} | {{ cep }}</v-card-text>
    <v-card-text>Área total: {{ area }} m2</v-card-text>
  </v-card>
</template>
<script>
export default {
  name: 'Warehouse',
  props: {
    id: Number,
    name: String,
    code: String,
    address: String,
    city: String,
    cep: String,
    area: Number
  }
}
</script>
<style>
  .card {
    text-align: left;
    margin-bottom: 10px;
    margin-top: 10px;
    width: 40%;
  }
</style>