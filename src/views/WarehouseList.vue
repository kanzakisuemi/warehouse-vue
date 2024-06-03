<template>
  <div>
    <h1>Galpões cadastrados</h1>

    <input type="text" placeholder="Buscar galpão" v-model="searchInput">

      <div v-for="warehouse in filteredWarehouses" :key="warehouse.id">
        <Warehouse
          :id="warehouse.id"
          :name="warehouse.name"
          :code="warehouse.code"
          :address="warehouse.address"
          :city="warehouse.city"
          :cep="warehouse.cep"
          :area="warehouse.area"
        />
      </div>
  </div>
</template>

<script>
import Warehouse from '@/components/Warehouse.vue'
export default {
  name: 'WarehouseList',
  components: {
    Warehouse
  },
  async mounted() {
    this.getWarehouses()
  },
  data() {
    return {
      warehouses: [],
      searchInput: ''
    }
  },
  methods: {
    async getWarehouses() {
      const response = await this.$http.get('http://localhost:3000/api/v1/warehouses')
      const result = await response.json()
      console.log(result)
      this.warehouses = result
      return this.warehouses
    }
  },
  computed: {
    filteredWarehouses() {
      return this.warehouses.filter(warehouse => {
        return warehouse.name.toLowerCase().includes(this.searchInput.toLowerCase())
      })
    }
  }
}

</script>

<style>

</style>