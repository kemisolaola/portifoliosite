<template>
  <v-app>
    <!-- nav bar -->
    <nav-bar :navProps="navProps" />
    <!-- Start of top container -->
    <v-container fluid class="top-container">
      <v-row justify="center ml-10 ml-lg-16">
        <v-col cols="12" sm="12" md="12" lg="10" class="mt-16 ml-md-16">
          <v-row class="ml-md-1 ml-lg-16">
            <v-col cols="12" sm="4" md="3" class="ml-md-6">
              <p class="profile-info font-weight-bold">
                I<span class="span-profile-class">’</span>M OLATUNJI
                OLUWAKEMI<span class="span-profile-class">.</span>
              </p>
              <p class="profile-info-role mb-2">FRONTEND DEVELOPER</p>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <!-- float container -->
    <v-row justify="center get-resume-container mx-0">
      <v-col
        cols="10"
        sm="6"
        md="6"
        lg="5"
        class="float-container text-center px-sm-10 px-md-16 pb-7 pb-sm-1 pb-md-10 pt-sm-12 pt-8"
      >
        <v-container class="pt-10 pb-13">
          <p class="profile-intro mt-13">
            Hello! I'm a frontend developer, skilled in creating engaging and
            interactive user interfaces for websites and web applications. I
            have a strong foundation in HTML, CSS and JavaScript and I'm
            experienced in using popular frontend frameworks such as Vue, Nuxt,
            React and Next. As a frontend developer, I enjoy collaborating with
            designers and backend developers to bring their visions to life and
            create seamless, user-centric interfaces.
          </p>
          <v-btn
            elevation="0"
            target="blank"
            href="Olatunji Resume.pdf"
            class="download-btn"
          >
            DOWNLOAD RESUME
          </v-btn>
        </v-container>
      </v-col>
    </v-row>
    <v-container class="mt-16 mb-3">
      <v-row justify="center" id="professional" class="">
        <v-col cols="12" sm="11" md="10">
          <p class="text-center font-weight-bod home-header mb-0">
            <span class="home-header-span">01 </span>PROFESSIONAL
          </p>
          <p class="text-center profession-subtitle">
            MY KNOWLEGDE LEVEL IN SOFTWARE
          </p>
          <h3>SKILLS</h3>
          <v-container fluid>
            <h4 class="skills-header">LANGUAGES</h4>
            <v-row>
              <v-col
                v-for="(language, index) in languages"
                cols="4"
                sm="2"
                :key="index"
                class="skills-set pr-1 pb-1"
              >
                {{ language }}
              </v-col>
            </v-row>
          </v-container>
          <v-container fluid class="mt-5">
            <h4 class="skills-header">JAVASCRIPT FRAMEWORKS AND LIBRARIES</h4>
            <v-row>
              <v-col
                v-for="(framework, index) in frameworks"
                cols="4"
                sm="2"
                :key="index"
                class="skills-set pr-1 pb-1"
              >
                {{ framework }}
              </v-col>
            </v-row>
          </v-container>
          <v-container fluid class="mt-5">
            <h4 class="skills-header">TOOLS</h4>
            <v-row>
              <v-col
                v-for="(tool, index) in tools"
                cols="4"
                sm="2"
                :key="index"
                class="skills-set pr-1 pb-1"
              >
                {{ tool }}
              </v-col>
            </v-row>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="mt-4" id="portifolio">
      <v-row justify="center" class="mt-13">
        <v-col cols="12">
          <p class="text-center font-weight-bold home-header mb-0">
            <span class="home-header-span">02 </span>PORTOFOLIO
          </p>
          <p class="text-center profession-subtitle">
            MY LATEST WORK. <span class="home-header-span"></span>
          </p>
          <v-container class="mt-15">
            <swiper ref="mySwiper" :options="swiperOption">
              <swiper-slide
                class="swiper"
                v-for="(picture, index) in photoCollections"
                :key="index"
                ><v-card
                  class="mx-auto mb-10"
                  max-width="344"
                  :href="picture.to"
                  hover
                >
                  <v-img :src="picture.img" height="200px" contain></v-img>

                  <v-card-title class="font-weight-medium">
                    {{ picture.name }}
                  </v-card-title>
                </v-card></swiper-slide
              >
              <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <!-- EXPERIENCE -->
    <v-container class="mt-7 mt-md-16" id="experience">
      <v-row justify="center" class="mt-16">
        <v-col cols="12" sm="9" md="9" lg="7">
          <p class="text-center font-weight-bold home-header mb-0">
            <span class="home-header-span">03 </span>EXPERIENCE
          </p>
          <v-container class="mt-5">
            <v-timeline align-top :dense="$vuetify.breakpoint.smAndDown">
              <v-timeline-item color="#F22E5D" small fill-dot>
                <v-card elevation="0" class="text-left">
                  <p class="timeline-date mb-0">Feb 2022 - Nov 2022</p>
                  <p class="hop mb-0">Sterling Bank Plc</p>
                  <p class="timeline-job-title mb-0">Frontend Developer</p>
                  <p class="timeline-job-info grey--text text--darken-2">
                    Worked in an Agile environment and collaborated with team
                    mates across various groups to achieve our goal. Led the
                    frontend team of the loan application solutions and expanded
                    scope of major bank web application, reducing customer
                    churn.
                  </p>
                </v-card>
              </v-timeline-item>
              <v-timeline-item color="#F22E5D" small fill-dot>
                <v-card elevation="0" class="text-md-right">
                  <p class="timeline-date mb-0">Feb 2021 - Feb 2022</p>
                  <p class="hop mb-0">Outfit.NG</p>
                  <p class="timeline-job-title mb-0">Frontend Developer</p>
                  <p class="timeline-job-info grey--text text--darken-2">
                    Contributed to the in-house UI library to create reusable
                    components that saved over 200 hours of development time per
                    month.Deployed new features to facilitate related procedures
                    & tools if necessary.
                  </p>
                </v-card>
              </v-timeline-item>
              <v-timeline-item color="#F22E5D" small fill-dot>
                <v-card elevation="0" class="text-left">
                  <p class="timeline-date mb-0">Feb 2019 - Jan 2021</p>
                  <p class="hop mb-0">Renostack Limited</p>
                  <p class="timeline-job-title mb-0">Frontend Developer</p>
                  <p class="timeline-job-info grey--text text--darken-2">
                    Responsible for building the user interface and developing
                    frontend architecture on various client projects using
                    several technologies and methodologies.
                  </p>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <!-- Contact Us -->
    <v-footer fluid class="contact-me pt-16" id="contact">
      <v-row justify="mt-16">
        <v-col cols="10" sm="10" md="9" lg="12">
          <v-container class="d-flex justify-space-between">
            <div class="d-flex">
              <a href="https://github.com/kemisolaola"
                ><v-icon class="mr-2"> mdi-github</v-icon></a
              >
              <a href="https://www.linkedin.com/in/oluwakemi-olatunji/"
                ><v-icon class="mr-2"> mdi-linkedin</v-icon></a
              >
            </div>
            <div>
              <small class="text-xs text-right"
                >© designed & built by Oluwakemi Olatunji ♥</small
              >
            </div>
          </v-container>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
import {
  Swiper,
  SwiperSlide,
} from "vue-awesome-swiper/dist/vue-awesome-swiper.js";
import "swiper/css/swiper.css";
import NavBar from "../components/NavBar";
export default {
  name: "Home",
  components: {
    NavBar,
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiperOption: {
        freeMode: true,
        spaceBetween: 1,
        pagination: {
          el: ".swiper-pagination",
          clickable: true,
        },
        breakpoints: {
          1000: {
            slidesPerView: 3,
            spaceBetween: 20,
          },
          768: {
            slidesPerView: 2,
            spaceBetween: 10,
          },
          640: {
            slidesPerView: 1,
            spaceBetween: 20,
          },
          320: {
            slidesPerView: 1,
            spaceBetween: 20,
          },

        }
      },
      navProps: {
        activeClass: {},
        elevation: "0",
        dark: "dark",
        navColor: "#f5f5f5",
        navBarItem: [
          { item: "HOME", route: "/" },
          { item: "PROFESSIONAL", route: "#professional" },
          { item: "EXPERIENCE", route: "#experience" },
          { item: "PORTIFOLIO", route: "#portifolio" },
          { item: "CONTACT", route: "#contact" },
        ],
      },
      languages: ["HTML", "CSS", "JAVASCRIPT", "TYPESCRIPT"],
      frameworks: [
        "VUE.JS",
        "NUXTJS",
        "VUEX",
        "TAILWIND",
        "VUETIFY",
        "BOOTSTRAP",
        "REACT",
        "NEXT.JS",
      ],
      tools: [
        "GIT",
        "GITHUB",
        "MICROSOFT AZURE",
        "VSCODE",
        "NETLIFY",
        "TRELLO",
      ],
      photoCollections: [
        {
          img: require("../assets/onebank-sterling.jpg"),
          name: "ONEBANK",
          to: "https://myonebank.sterling.ng/",
        },
        {
          img: require("../assets/tbh-sterling.jpg"),
          name: "THE BUSINESS HUB",
          to: "https://thebusinesshub.ng/",
        },
        {
          img: require("../assets/fortvest.jpg"),
          name: "FORTVEST",
          to: "https://myfortvest.ng/",
        },
        {
          img: require("../assets/dice.jpg"),
          name: "DICE MESSENGER",
          to: "http://dicemessenger.com/",
        },
      ],
      items: [
        {
          color: "#F22E5D",
          icon: "mdi-star",
        },
        {
          color: "#F22E5D",
        },
        {
          color: "#F22E5D",
          icon: "mdi-airballoon",
        },
        {
          color: "#F22E5D",
          icon: "mdi-buffer",
        },
      ],
    };
  },
};
</script>
<style scoped>
@media (min-width: 768px) {
  .top-container {
    background: #e2e2e4;
    /* background-image: url("../assets/profile-image.png"); */
    background-repeat: no-repeat;
    background-size: contain;
    background-position: 85%;
    padding-bottom: 200px;
  }
}

@media (max-width: 767px) {
  .top-container {
    background: #e2e2e4;
    padding-bottom: 200px;
  }
}

.profile-info {
  font-size: 40px;
  line-height: 40px;
}
.profile-info-role {
  color: #000000;
  font-size: 16px;
  line-height: 10px;
}
.span-profile-class {
  color: #f22e5d;
}
.float-container {
  background: #fff8f9;
}
.get-resume-container {
  margin-top: -130px;
}
.download-btn {
  width: 200px;
  height: 50px;
  background: #fff8f9 !important;
  border: 1px solid #f22e5d !important;
  color: #f22e5d !important;
}
.profile-intro {
  font-size: 13px;
  line-height: 20px;
  font-weight: 600;
  font-family: "Inter";
  color: black;
}
.skills-set {
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  color: #616161;
  line-height: 21px;
  display: inline-block;
  letter-spacing: 0.01em;
  text-align: left;
}
.skills-header {
  color: #343232;
  text-align: left;
}
.home-header-span {
  color: #616161;
}
.home-header {
  font-size: 35px;
  font-style: normal;
  font-weight: 700;
  letter-spacing: 0em;
}
.profession-subtitle {
  font-size: 18px;
  font-style: normal;
  font-weight: 400;
  letter-spacing: 0.01em;
}
.v-timeline-item__dot {
  z-index: 2;
  border-radius: 50%;
  box-shadow: 0px 2px 1px -1px rgb(0 0 0 / 20%),
    0px 1px 1px 0px rgb(0 0 0 / 14%), 0px 1px 3px 0px rgb(0 0 0 / 12%);
  height: 25px;
  left: calc(50% - 19px);
  width: 38px;
}
.timeline-date {
  font-weight: 500;
  font-size: 12px;
  line-height: 16px;
  color: #f22e5d;
}
.hop {
  font-style: normal;
  font-weight: normal;
  font-size: 22px;
  line-height: 35px;
}
.theme--light.v-timeline:before {
  background: #f22e5d;
}
.v-timeline::before {
  top: 24px;
  height: calc(100% - 65px);
}
.timeline-job-title {
  font-style: normal;
  font-weight: 500;
  font-size: 13px;
  line-height: 35px;
  color: #000000;
}
.timeline-job-info {
  font-style: normal;
  font-weight: normal;
  font-size: 14px;
  line-height: 25px;
}
.contact-me {
  background: #fff8f9;
}

.swiper-pagination >>> .swiper-pagination-bullet {
  opacity: 1;
  background-color: #d7dce4 !important;
  width: 6px;
  height: 6px;
}

.swiper-pagination >>> .swiper-pagination-bullet-active {
  background-color: #8b98b1 !important;
}
</style>
