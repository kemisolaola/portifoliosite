<template>
  <v-app>
      <v-navigation-drawer color="#FFF8F9" app width="200" overlay-opacity="0" permanent class="pt-7 pt-lg-2" v-model="drawer" :mini-variant="$vuetify.breakpoint.mdAndDown">
          <v-img src="../assets/logo.png" width="50" class="mx-auto mb-16"></v-img>
           <v-list dense class="mt-10 px-3 font-weight-bold" flat  rounded>
      <v-list-item-group
        v-model="selectedItem"
        color="#F22E5D"
      >
        <v-list-item class="mb-3 mb-lg-0"
          v-for="(item, i) in sideBarItems1"
          :key="i"
        >
          <v-list-item-icon class="mr-1">
            <v-icon v-text="item.icon" small></v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text">{{item.text}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
        <v-divider></v-divider>
         <v-list dense class="mt-10 px-3" flat  rounded>
      <v-list-item-group
        v-model="selectedItem2"
        color="#F22E5D"
      >
        <v-list-item class="mb-3 mb-lg-0"
          v-for="(item, i) in sideBarItems2"
          :key="i"
        >
          <v-list-item-icon class="mr-1">
            <v-icon v-text="item.icon" small></v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="item.text"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
    <!-- <v-img src="../assets/avatar.png" width="50" class="mx-auto mt-9"></v-img> -->
    <template v-slot:append>
      <div class="pa-2">
            <v-img src="../assets/avatar.png" width="50" class="mx-auto mt-9"></v-img>
                <p class="text-center profile-name">Briget Mary</p>
      </div>
    </template>
      </v-navigation-drawer>
      <v-container class="mt-3" >
          <v-row justify=" mr-2 mr-md-10">
            <v-spacer></v-spacer>
              <v-col class="text-right">
                <v-tooltip bottom>
                  <template v-slot:activator="{ on, attrs }">
                    <span
                      v-bind="attrs"
                      v-on="on"
                    >
                    <v-icon x-large color="#AAA9A9">mdi-bell</v-icon>
                      </span>
                  </template>
                  <span>Notification</span>
                </v-tooltip>
              </v-col>
          </v-row>
          <v-container class="mt-9 ml-3">
              <p class="font-weight-bold">Dashboard</p>
              <v-row class="mr-2 mr-md-14 mt-6">
                  <v-col cols="11" sm="5" md="5" lg="4" v-for="(card, index) in cardInfo" :key="index">
                      <v-card elevation="0" outlined class="pl-3 py-9 ">
                          <p class=" card-detail">{{ card.text}}</p>
                          <p class="card-num">{{ card.num }}</p>
                      </v-card>
                  </v-col>
              </v-row>
          </v-container>
          <v-container class="mt-9 ml-3">
              <p class="font-weight-bold">Transaction History</p>
              <v-row class="mr-2 mr-md-14 mt-6 pb-16">
                  <v-col cols="12">
                  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            <v-checkbox  v-model="checkbox" color="#C4C4C4"  class="my-checkbox" label="Service Type"></v-checkbox>
          </th>
          <th class="text-left">
            Service Cost
          </th>
          <th class="text-left">
            Technician
          </th>
          <th class="text-left">
            Review
          </th>
          <th class="text-left">
            Date
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="(item, index) in services"
          :key="index"
          class="grey--text text--lighten-1 table-content"
        >
          <td>            <v-checkbox  v-model="checkbox" color="#C4C4C4"  class="my-checkbox-data" :label=item.type></v-checkbox>
</td>
          <td>{{ item.costs }}</td>
          <td>{{ item.technician }}</td>
          <td>{{ item.rate }}</td>
          <td>{{ item.date }}</td>
        </tr>
      </tbody>
    </template>
                </v-simple-table>
                </v-col>
              </v-row>
          </v-container>
      </v-container>
  </v-app>
</template>

<script>
export default {
  name: "Signup",
  components: {
    // NavBar,
  },
  data () {
    return {
      drawer: true,
      navProps: {
        navText: 'small',
        activeClass: 'red--text text--lighten-1 no-active',
        elevation: '0',
        dark: 'dark',
        navColor: '#FFFFFF',
        navBarItem: [
          {icons: 'mdi-bell', route: '/'},
        ]
      },
      selectedItem: 1,
      sideBarItems1: [
        { text: 'Dashboard', icon: 'mdi-view-dashboard' },
        { text: 'Technician', icon: 'mdi-account-multiple' },
        { text: 'Services', icon: 'mdi-phone' },
        { text: 'Location', icon: 'mdi-map-marker' }
      ],
      selectedItem2: 1,
      sideBarItems2: [
        { text: 'Profile', icon: 'mdi-account' },
        { text: 'Settings', icon: 'mdi-cog-outline' },
        { text: 'Log out', icon: 'mdi-logout' }
      ],
      cardInfo: [
          {text: 'TRANSACTIONS SUCCESSFUL', num: 11},
          {text: 'TRANSACTIONS PENDING', num: 9},
          {text: 'TRANSACTIONS FAILED', num: 452}
      ],
      services: [
          { type: 'Auto Works', costs: '#5000', technician: 'Moses Adamu', rate: 4.3, date: '21/2/2012' },
          { type: 'Auto Painting', costs: '#5000', technician: 'Moses Adamu', rate: 4.3, date: '21/2/2012' },
          { type: 'Wheel balancing', costs: '#5000', technician: 'Moses Adamu', rate: 4.3, date: '21/2/2012' },
        ]
    }
  }
}
</script>
<style scoped>
.card-detail {  
font-style: normal;
font-weight: 500;
font-size: 18px;
line-height: 22px;
letter-spacing: -0.02em;
}
.card-num {  
font-style: normal;
font-weight: 500;
font-size: 28px;
line-height: 22px;
letter-spacing: -0.02em;
color: #f22e5d;
}
.v-data-table::v-deep th {
  font-size: 13px !important;
}
.v-data-table::v-deep td {
  font-size: 12px !important;
}
.my-checkbox .v-label {
  font-size: 13px;
} 
::v-deep .my-checkbox .v-label {
 font-size: 13px;
}
.my-checkbox-data .v-label {
  font-size: 12px;
  color: #bdbdbd;
} 
.profile-name {
  font-size: 12px;
  color: #bdbdbd;
} 
::v-deep .my-checkbox-data .v-label {
 font-size: 12px;
  color: #aaa9a9;
}
</style>