<template>
  <div class="card">
    <h3>{{ name }} - {{ code }}</h3>
    <address>
      <p>Endereço: {{ address }}</p>
      <p>Cidade: {{ city }}</p>
      <p>Área total: {{ area }} m2</p>
    </address>
      
  </div>
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
    area: Number
  }
}
</script>
<style>
  .card {
    border-style: solid;
    border-width: 1px;
    border-radius: 10px;
    margin-top: 10px;
    width: 40%;
    margin-left: auto;
    margin-right: auto;
  }
</style>