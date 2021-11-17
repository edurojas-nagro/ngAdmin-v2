<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <!--  -->
      <v-list disabled>
        <v-subheader>Dashboard</v-subheader>
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item v-for="(item, i) in items" :key="i" :class='item.classe'>
            <v-list-item-content>
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
             <v-list-item-icon>
              <v-icon v-text="item.icon" :class='item.classe'></v-icon>
            </v-list-item-icon>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app id="barraNav">
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        color="white"
      ></v-app-bar-nav-icon>

      <v-toolbar-title>
        <v-img
          max-height="150"
          max-width="250"
          :src="require('../assets/img/logo.svg')"
        ></v-img>
      </v-toolbar-title>
    </v-app-bar>

    <v-main>
      <!--  -->
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: ()=> {
    return {
      drawer: null,
      items: [
        { text: "Empresas", icon: "mdi-domain", classe: 'active cursorActive'},
        { text: "Produtos", icon: "mdi-check", classe: 'cursorActive'},
        { text: "Serviços", icon: "mdi-flag", classe: 'cursorActive' },
      ],
    }
  },
};
</script>
<style scoped>
#barraNav {
  background-color: #093677;
}

.active{
  background-color: #0DB5B5;
  color: white !important;
}

.cursorActive{
  cursor: pointer;
}

.cursorActive:hover{
  cursor: pointer;
  background-color: #0DB5B5;
  color: white !important;
}
</style>
