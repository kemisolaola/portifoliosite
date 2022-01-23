<template>
  <v-app class="main-container">
    <!-- nav bar -->
    <nav-bar-dashboard :navProps="navProps" />
    <!-- Start of top container -->
    <v-container fluid class="top-container mt-16 mt-lg-16">
      <v-row justify="center">
        <v-col cols="10" sm="5" lg="4" class="mt-16">
          <p class="signin-title font-weight-black">Sign In to Order for a Service</p>
          <div class="pt-10">
          <p class="signin-text mb-1 mt-16 d-none d-sm-flex"> If you don’t have an account?</p>
          <p class="signin-text mt-0 d-none d-sm-flex">You can <router-link to="/signup"><span class="signin-text-span"> Sign Up!</span></router-link></p>
          </div>
        </v-col>
        <v-col cols="12" sm="6" md="5" lg="4">
          <v-form>
            <v-row>
              <v-col cols="12">
                <v-text-field label="Username" solo flat background-color="#FFF8F9"></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Email" solo flat background-color="#FFF8F9"></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field label="Password" type="passsword" solo flat background-color="#FFF8F9"></v-text-field>
              </v-col>
              <v-col cols="12" class="text-right">
                <p class="form-subtext">Recovery password</p>
              </v-col>
              <v-col cols="12" class="text-right">
                <v-btn color="#F22E5D" block dark height="40">SIGN IN</v-btn>
              </v-col>
              <v-col cols="12" class="text-center">
                <v-row wrap no-gutters>
                    <v-col cols="4" class="text-center mt-2">
                        <v-divider />
                    </v-col>
                    <v-col cols="4" class="text-center mt-0">
                      <p class="form-subtext">or continue with</p>
                    </v-col>
                    <v-col cols="4" class="text-center mt-2">
                        <v-divider/>
                    </v-col>
                </v-row>
                  </v-col>
              <v-col cols="12" class="text-center">
                <v-icon class="mr-3">mdi-instagram</v-icon>
                <v-icon class="mr-3">mdi-linkedin</v-icon>
                <v-icon class="mr-3">mdi-facebook</v-icon>
                <v-icon class="mr-1">mdi-twitter</v-icon>
              </v-col>
              <v-col cols="12" class="hidden-sm-and-up text-center">
                <p class="signin-text text-center"> If you don’t have an account?</p>
               <p class="signin-text mt-0">You can <router-link to="/signup"><span class="signin-text-span"> Sign Up!</span></router-link></p>
              </v-col>
            </v-row>
          </v-form>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import NavBarDashboard from '../components/NavBarDashboard.vue';
export default {
  name: "Signin",
  components: {
    NavBarDashboard,
  },
  data () {
    return {
      navProps: {
        navText: 'small',
        activeClass: 'red--text text--lighten-1 no-active',
        elevation: '0',
        dark: 'dark',
        navColor: '#FFFFFF',
        navBarItem: [
          {item: 'Technicians', route: '/', icon: 'mdi-account-multiple'},
          {item: 'Order', route: '/order', icon: 'mdi-cart'},
          {item: 'About Us', route: '/aboutus', icon: 'mdi-information-outline'},
          {item: 'Dashboard', route: '/dashboard', icon: 'mdi-translate'},
          {item: 'Signin', route: '/signin', icon: 'mdi-login-variant'},
          {item: 'Signup', route: '/signup', icon: 'mdi-login-variant'}
        ]
      }
    }
  }
}
</script>
<style scoped>
.main-container {
  background: url('../assets/ellipselarge.png'), url('../assets/ellipse.png') ;
  background-repeat: no-repeat;
  background-position: bottom left, bottom left;
}
.signin-title {
  font-size: 45px;
}
.signin-text {
  font-size: 15px;
font-weight: 600;
line-height: 17px;
letter-spacing: 0.03em;
}
.signin-text-span {
  color: #F22E5D;
}
.form-subtext{
  font-weight: bold;
font-size: 12px;
line-height: 19px;
letter-spacing: 0.02em;
text-indent: 2px;
color: rgba(18, 18, 18, 0.35);
}
a {
  text-decoration: none;
}
</style>