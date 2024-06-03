<template>
  <div>
    <h1>Cadastrar Galpão</h1>
    <div class="container">
      <p>{{ msg }}</p>
      <form v-on:submit.prevent>
        <div class="form">
          <label>Nome: </label>
          <input v-model="form.name" type="text" placeholder="Nome do Galpão" />
        </div>
        <div class="form">
          <label>Código: </label>
          <input type="text" v-model="form.code" placeholder="Código do Galpão" />
        </div>
        <div class="form">
          <label>Endereço: </label>
          <input type="text" v-model="form.address" placeholder="Endereço do Galpão" />
        </div>
        <div class="form">
          <label>CEP: </label>
          <input type="text" v-model="form.cep" placeholder="CEP" />
        </div>
        <div class="form">
          <label>Cidade: </label>
          <input type="text" v-model="form.city" placeholder="Cidade" />
        </div>
        <div class="form">
          <label>Área m2: </label>
          <input type="number" v-model="form.area" />
        </div>
        <div class="form">
          <label>Descrição: </label>
          <textarea v-model="form.description" cols="30" rows="10"></textarea>
        </div>
        <div>
          <button type="submit" v-on:click="createWarehouse">Cadastrar</button>
        </div>
      </form>
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