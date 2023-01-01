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
              <p class="profile-info-role mb-2">SOFTWARE DEVELOPER</p>
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
            I am a Frontend developer with industry experience building websites
            and web applications. I specialize in JavaScript and have
            professional experience working with Vue.js. I also have experience
            working with and React and Node.js in an agile environment.
          </p>
          <v-btn
            elevation="0"
            href="Oluwakemi_Shalewa Olatunji_Resume.pdf"
            class="download-btn"
          >
            DOWNLOAD RESUME
          </v-btn>
        </v-container>
      </v-col>
    </v-row>
    <v-container class="mt-16" fluid>
      <v-row justify="center" id="professional" class="">
        <v-col cols="12" sm="11" md="10">
          <p class="text-center font-weight-bold home-header mb-0">
            <span class="home-header-span">01 </span>PROFESSIONAL
          </p>
          <p class="text-center profession-subtitle">
            MY KNOWLEGDE LEVEL IN SOFTWARE
          </p>
          <v-container class="mt-15" fluid>
            <div class="d-flex justify-center">
              <p
                class="skills-set text-right px-3"
                style="color: #f22e5d"
                v-for="(skill, index) in progressBar"
                :key="index"
              >
                {{ skill.skills }}
              </p>
            </div>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="mt-3" id="portifolio">
      <v-row justify="center" class="mt-5">
        <v-col cols="12">
          <p class="text-center font-weight-bold home-header mb-0">
            <span class="home-header-span">02 </span>PORTOFOLIO
          </p>
          <p class="text-center profession-subtitle">
            MY LATEST WORK. <span class="home-header-span"> SEE MORE ></span>
          </p>
          <v-container class="mt-10">
            <v-row no-gutters justify="center">
              <img
                v-for="(picture, index) in photoCollections"
                :key="index"
                :src="picture"
                width="30%"
                height="30%"
                contain
              />
            </v-row>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <!-- EXPERIENCE -->
    <v-container class="mt-7 mt-md-16" id="experience" fluid>
      <v-row justify="center" class="mt-2">
        <v-col cols="12" sm="10" md="10">
          <p class="text-center font-weight-bold home-header mb-0">
            <span class="home-header-span">03 </span>EXPERIENCE
          </p>
          <v-container class="mt-5">
            <v-timeline align-top :dense="$vuetify.breakpoint.smAndDown">
              <v-timeline-item color="#F22E5D" small fill-dot>
                <v-card elevation="0" class="text-left">
                  <p class="timeline-date mb-0">2022</p>
                  <p class="hop mb-0">Sterling Bank Plc</p>
                  <p class="timeline-job-title mb-0">Software Developer</p>
                  <ul class="timeline-job-info grey--text text--darken-2 pl-0">
                    <li>
                      Re-configured loan processing for SMEs, increasing
                      efficiency.
                    </li>
                    <li>
                      Developed admin system for savings application, enabling
                      admins to track customers transactions.
                    </li>
                    <li>
                      Deployed new features to facilitate related procedures &
                      tools if necessary
                    </li>
                    <li>
                      Participated in architecture discussions and discussed
                      solutions to system directly related to my area of focus.
                    </li>
                  </ul>
                </v-card>
              </v-timeline-item>
              <v-timeline-item color="#F22E5D" small fill-dot>
                <v-card elevation="0" class="text-md-right">
                  <p class="timeline-date mb-0">2021 - 2022</p>
                  <p class="hop mb-0">Outfit.NG</p>
                  <p class="timeline-job-title mb-0">Creative Design Lead</p>
                  <ul class="timeline-job-info grey--text text--darken-2">
                    <li>
                      Added features to a savings application enabling the users
                      save money.
                    </li>
                    <li>
                      Expanded scope of major bank web application,reducing
                      customer churn.
                    </li>
                    <li>
                      Re-configured loan processing for SMEs, increasing
                      efficiency.
                    </li>
                    <li>
                      Monitored websites' performance to ensure smooth user
                      experience.
                    </li>
                    <li>
                      Played major roles in the implementation of a new upgraded
                      system.
                    </li>
                  </ul>
                </v-card>
              </v-timeline-item>
              <v-timeline-item color="#F22E5D" small fill-dot>
                <v-card elevation="0" class="text-left">
                  <p class="timeline-date mb-0">2019 - 2021</p>
                  <p class="hop mb-0">RenoStack</p>
                  <p class="timeline-job-title mb-0">Frontend Developer</p>
                  <ul class="timeline-job-info grey--text text--darken-2 pl-0">
                    <li>
                      Successfully developed & implemented car rental, bid, &
                      project management systems.
                    </li>
                    <li>
                      Successfully wrote code for various web applications and
                      websites.
                    </li>
                    <li>
                      Documented test plans, testing procedures & results.
                    </li>
                    <li>
                      Successfully collaborated with internal teams to execute
                      work and meet schedule and budget expectations.
                    </li>
                  </ul>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </v-container>
        </v-col>
      </v-row>
    </v-container>
    <!-- Contact Us -->
    <v-container fluid class="contact-me py-16" id="contact">
      <v-row justify="center mt-4 pb-16">
        <v-col cols="10" sm="10" md="9" lg="7">
          <v-row justify="center">
            <v-col cols="12" sm="5" md="4">
              <p class="grey--text text--darken-2 font-weight-bold">CONTACT</p>
              <p class="timeline-job-info grey--text text--darken-2">
                I'm a paragraph. Click here to add your own text and edit me.
                It’s easy. Just click “Edit Text” or double click me to add your
                own content and make changes.
              </p>
              <p class="timeline-job-info grey--text text--darken-2">
                bridgetmary.@gmail.com
              </p>
              <p class="timeline-job-info grey--text text--darken-4">
                Tel: 080 7890 8982
              </p>
            </v-col>
            <v-col cols="12" sm="6">
              <v-form>
                <v-row>
                  <v-col cols="12" sm="6" class="my-0 py-0">
                    <v-text-field
                      label="Name"
                      outlined
                      color="#DEB9C2"
                      class="mb-0"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="6" class="my-0 py-0">
                    <v-text-field
                      label="Email"
                      outlined
                      color="#DEB9C2"
                      class="mb-0"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" class="my-0 py-0">
                    <v-text-field
                      label="Phone"
                      outlined
                      color="#DEB9C2"
                      class="mb-0"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" class="my-0 py-0">
                    <v-textarea
                      label="Message"
                      outlined
                      color="#DEB9C2"
                      class="mb-0"
                    >
                    </v-textarea>
                  </v-col>
                  <v-col class="my-0 py-0">
                    <v-btn
                      color="#F22E5D"
                      flat
                      width="100%"
                      dark
                      height="55"
                      depressed
                      tile
                      >Send</v-btn
                    >
                  </v-col>
                </v-row>
              </v-form>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
import NavBar from "../components/NavBar";
export default {
  name: "Home",
  components: {
    NavBar,
  },
  data() {
    return {
      navProps: {
        activeClass: {},
        elevation: "3",
        dark: "dark",
        navColor: "#E2E2E4",
        navBarItem: [
          { item: "HOME", route: "/" },
          { item: "PROFESSIONAL", route: "#professional" },
          { item: "EXPERIENCE", route: "#experience" },
          { item: "PORTIFOLIO", route: "#portifolio" },
          { item: "CONTACT", route: "#contact" },
        ],
      },
      progressBar: [
        { skills: "JAVASCRIPT" },
        { skills: "HTML" },
        { skills: "CSS" },
        { skills: "VUE.JS" },
        { skills: "NUXT" },
        { skills: "REACT" },
        { skills: "RESTAPI" },
        { skills: "GRAPHQL" },
        { skills: "BOOTSTRAP" },
        { skills: "VUETIFY" },
        { skills: "TAILWIND CSS" },
        { skills: "GIT" },
        { skills: "GITHUB" },
      ],
      photoCollections: [
        require("../assets/laptops.png"),
        require("../assets/headset.png"),
        require("../assets/phone.png"),
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
ul {
  list-style: none;
}
.top-container {
  background: #e2e2e4;
  background-image: url("../assets/profile-image.png");
  background-repeat: no-repeat;
  background-size: contain;
  background-position: 85%;
  padding-bottom: 200px;
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
  font-size: 12px;
  font-style: normal;
  font-weight: 400;
  line-height: 21px;
  letter-spacing: 0.01em;
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
</style>
