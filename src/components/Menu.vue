<template lang="">
  <div>
    <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">Sobre</router-link> |
      <router-link to="/warehouses">Galpões</router-link> |
      <router-link to="/warehouses/new">Novo Galpão</router-link>
    </nav>
  </div>
</template>
<script>
export default {
  name: 'Menu'
}
</script>

<style>
  nav {
    padding: 30px;
  }

  nav a {
    font-weight: bold;
    color: #2c3e50;
  }

  nav a.router-link-exact-active {
    color: #42b983;
  }
</style>