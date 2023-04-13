<template>
    <nav>
        <v-app-bar app :color = navProps.navColor dark class="pl-4 px-lg-16" :elevation= navProps.elevation>
      <div class="d-flex align-center">
        <v-img
          alt="portifolio"
          class="shrink ml-16-lg mr-1 mr-lg-16"
          contain
          src="../assets/logo.png"
          transition="scale-transition"
          width="40"
        />
      </div>
      <v-spacer></v-spacer>
    <div class="ml-10 ml-lg-16 d-none d-md-flex" v-for="(item, index) in navProps.navBarItem" :key="index">

      <v-btn
       color="#616161"
      class="nav-btn font-weight-bold   "
      active-class= "active-class-nav red--text text--accent-3 no-active text"
        :to="item.route"
        text
      >
      <!-- <v-icon v-if="item.icons"> {{item.icons}}</v-icon> -->
        <span class="mr-2">{{item.item}}</span>
      </v-btn>
    </div>
    <v-spacer class="hidden-md-and-up"></v-spacer>
    <v-icon class="hidden-md-and-up pl-0" large  @click="drawer = !drawer" color="black">mdi-menu</v-icon>
    </v-app-bar>
    <v-navigation-drawer
    v-model="drawer"
      disable-resize-watcher
      app
      width="260"
      dark
      right
      color = '#FFF8F9' class="d-flex d-lg-none">
           <v-app-bar color="#FFF8F9" dark class="pl-0">
             <v-spacer></v-spacer>
             <!-- <v-img contain width="50" height="50" src="../assets/logo.png"></v-img> -->
               <v-icon class="hidden-lg-and-up pl-0" large  @click="drawer = !drawer" color="black">mdi-close</v-icon>
               </v-app-bar>
      <v-list dense class="mt-10 px-3 font-weight-bold" flat  rounded>
      <v-list-item-group active-class="red-text text--accent-2"
        v-model="selectedItem" dark
      >
        <v-list-item :href="item.route"
          v-for="(item, index) in navProps.navBarItem" :key="index"
        >
         <v-list-item-icon class="mr-1">
            <v-icon v-text="item.icon" small color="grey darken--2"></v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="grey--text" v-text="item.item"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
    </v-navigation-drawer>
    </nav>
</template>
<script>
export default {
    props: ['navProps'],
    data () {
        return {
          drawer: false
        }
    }
}
</script>
<style scoped>
.active-class-nav{
    font-weight: 600;
    background-image: url('../assets/line.png');
    background-position: bottom;
}
.v-btn.v-size--default {
    font-size: 16px;
}
.v-btn--active.no-active::before {
  opacity: 0 !important;
  /* color: #F22E5D !important; */
}
</style>