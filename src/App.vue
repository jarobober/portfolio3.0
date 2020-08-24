<template>
  <v-app>
    <v-navigation-drawer
      light
      color="#16987390"
      height="296"
      class="rounded drawer"
      v-model="drawer"
      floating
      fixed
      temporary
    >
      <v-list>
        <v-list-item
          v-for="item in navigationLinks"
          :key="item.name"
          link
          @click="$vuetify.goTo(item.target, {duration: '800', easing: 'easeInOutCubic'}); close();"
        >
          <v-list-item-icon>
            <v-icon>
              {{ item.icon}}
            </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="white--text">
              {{ item.name }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
     <v-app-bar dark fixed collapse-on-scroll flat color="transparent">
      <v-app-bar-nav-icon 
        color="#19b387" 
        class="ml-md-1 icon" 
        @click="drawer = !drawer"
        >
          <v-icon large>
            mdi-menu
          </v-icon>
        </v-app-bar-nav-icon>
        <v-toolbar-title 
          class="navigation-bar__header-name"
          >
          <header
            class="font-weight-light"
            >
            Jaroslaw Bober
          </header>
        </v-toolbar-title>
      </v-app-bar>
    <HeroPage class="hero" />
    <SectionSkills />
    <SectionDivider />
    <SectionProjects />
    <SectionAbout />
    <SectionContact />
    <FooterComponent />
  </v-app>
</template>

<script>
import HeroPage from "./components/HeroPage";
import SectionSkills from "./components/SectionSkills";
import SectionDivider from "./components/SectionDivider";
import SectionProjects from "./components/SectionProjects";
import SectionAbout from "./components/SectionAbout";
import SectionContact from "./components/SectionContact";
import FooterComponent from "./components/FooterComponent";

export default {
  name: "App",
  components: {
    HeroPage,
    SectionSkills,
    SectionDivider,
    SectionProjects,
    SectionAbout,
    SectionContact,
    FooterComponent
  },
  data: function() {
    return{
      drawer: false,
      navigationLinks: [
        {
          name: "Home",
          icon: "mdi-home",
          target: "#hero-page"
        },
        {
          name: "Skills",
          icon: "mdi-hammer-wrench",
          target: "#section-skills "
        },
        {
          name: "Projects",
          icon: "mdi-briefcase",
          target: "#section-projects"
        },
        {
          name: "About me",
          icon: "mdi-account-circle",
          target: "#section-about"
        },
        {
          name: "Contact",
          icon: "mdi-email",
          target: "#section-contact"
        },
      ]
    };
  },
  methods: {
    close() {
      this.drawer = false
    },
  }
};
</script>

<style lang="scss">

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: hidden;
}

body {
  position: relative;
}

.drawer {
  margin-top: 65px;
  margin-left: 15px;
}

.hero {
  position: absolute;
  top: 0;
  left: 0;
}

</style>
