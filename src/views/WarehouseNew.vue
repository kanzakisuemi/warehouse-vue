<template>
  <div>
    <h1>Cadastrar Galpão</h1>
    <div class="container">
      <v-alert v-if="msg" type="info">{{ msg }}</v-alert>
      <v-form v-on:submit.prevent>
        <v-text-field label="Nome" v-model="form.name"></v-text-field>
        <v-text-field label="Código" v-model="form.code"></v-text-field>
        <v-text-field label="Endereço" v-model="form.address"></v-text-field>
        <v-text-field label="CEP" v-model="form.cep"></v-text-field>
        <v-text-field label="Cidade" v-model="form.city"></v-text-field>
        <v-text-field label="Área" v-model="form.area"></v-text-field>
        <v-textarea label="Descrição" v-model="form.description"></v-textarea>
        
        <v-btn color="primay" v-on:click="createWarehouse">Cadastrar</v-btn>
      </v-form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'WarehouseNew',
  data() {
    return {
      msg: '',
      form: {
        name: '',
        code: '',
        address: '',
        cep: '',
        city: '',
        area: '',
        description: ''
      }
    }
  },
  methods: {
    async createWarehouse() {
      try {
        await this.$http.post('http://localhost:3000/api/v1/warehouses', {
          name: this.form.name,
          code: this.form.code,
          address: this.form.address,
          cep: this.form.cep,
          city: this.form.city,
          area: this.form.area,
          description: this.form.description
        })
        this.msg = 'Galpão cadastrado com sucesso!'
      } catch (error) {
        this.msg = 'Ops :( algo deu errado, tente novamente!'
        console.log(error)
      }
    }
  }
}

</script>

<style>
  .form {
    margin-bottom: 10px;
  }
</style>