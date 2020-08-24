<template>
  <v-footer color="#e5e5e5" padless>
    <v-container>
      <v-row justify="center">
        <v-tooltip
          v-for="(item, i) in footer"
          :key="i"
          top
        >
          <template v-slot:activator="{ on, attrs }">
            <v-btn 
              text
              @click="$vuetify.goTo(item.target, {duration: '800', easing: 'easeInOutCubic'});"
              v-bind="attrs"
              v-on="on"
            >
              <v-icon>
                {{ item.icon }}
              </v-icon>
            </v-btn>
          </template>
          <span>
            {{ item.name }}
          </span>
        </v-tooltip>
      </v-row>
      <v-row justify="center" align="center">
        <v-col>
          <v-divider></v-divider>
        </v-col>
      </v-row>
      <v-row justify="center" align="center">
          <h5>2020 copyrights by JARO</h5>
      </v-row>
    </v-container>
    </v-footer>
</template>

<script>
export default {
  name: "FooterComponent",
  data: function() {
    return {
      footer: [
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
          name: "About",
          icon: "mdi-account-circle",
          target: "#section-about"
        },
        {
          name: "Contact",
          icon: "mdi-email",
          target: "#section-contact"
        }
      ]
    }
  }
}
</script>