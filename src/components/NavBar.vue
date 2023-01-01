<template>
  <nav class="px-0 mx-0">
    <v-app-bar
      app
      :color="navProps.navColor"
      dark
      class="pl-7 px-sm-12 px-md-16"
      :elevation="navProps.elevation"
    >
      <div class="ml-md-3 ml-lg-0 text-h4" style="color: #f22e5d;">
        KEMI.
      </div>
      <v-row justify="center">
        <v-col cols="10">
          <div class="ml-16 d-flex justify-center text-center">
          <v-btn
          v-for="(item, index) in navProps.navBarItem"
          :key="index"
          color="#616161"
          class="nav-btn font-weight-regular"
          :href="item.route"
          active-class="active-class-nav red--text text--lighten-2 no-active text"
          text
        >
          <span class="mr-2">{{ item.item }}</span>
        </v-btn>
        </div>
      </v-col>
      </v-row>
      <v-spacer class="hidden-lg-and-up"></v-spacer>
      <v-icon
        class="hidden-lg-and-up pl-0"
        large
        @click="drawer = !drawer"
        color="black"
        >mdi-menu</v-icon
      >
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      disable-resize-watcher
      app
      width="260"
      dark
      right
      :color="navProps.navColor"
      class="d-flex d-lg-none"
    >
      <v-app-bar color="white" dark class="pl-0">
        <v-spacer></v-spacer>
        <!-- <v-img contain width="50" height="50" src="../assets/logo.png"></v-img> -->
        <v-icon
          class="hidden-lg-and-up pl-0"
          large
          @click="drawer = !drawer"
          color="black"
          >mdi-close</v-icon
        >
      </v-app-bar>
      <v-list dense class="mt-10 px-3 font-weight-bold" flat rounded>
        <v-list-item-group v-model="selectedItem" dark>
          <v-list-item
            :href="item.route"
            v-for="(item, index) in navProps.navBarItem"
            :key="index"
          >
            <v-list-item-content>
              <v-list-item-title
                class="grey--text"
                v-text="item.item"
              ></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-list-item to="/signin">
            <v-list-item-content>
              <v-list-item-title class="grey--text">SIGNIN</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  props: ["navProps"],
  data() {
    return {
      drawer: false,
    };
  },
};
</script>
<style scoped>
.active-class-nav {
  font-weight: 600;
}
.v-btn.v-size--default {
  font-size: 16px;
}
.v-btn--active.no-active::before {
  opacity: 0 !important;
  /* color: #F22E5D !important; */
}
</style>
