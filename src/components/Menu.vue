<template lang="">
  <div>
    <v-container>
      <v-row>
        <v-col>
          <v-toolbar>
            <v-toolbar-title>Galpões do Pedro</v-toolbar-title>
            <v-spacer></v-spacer>
            <nav>
              <v-btn text color="grey" to="/">Home</v-btn>
              <v-btn text color="grey" to="/about">Sobre Pedro</v-btn>
              <v-btn text color="grey" to="/warehouses">Galpões</v-btn>
              <v-btn text color="grey" to="/warehouses/new">Novo Galpão</v-btn>
              
            </nav>
          </v-toolbar>
        </v-col>
      </v-row>
    </v-container>
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