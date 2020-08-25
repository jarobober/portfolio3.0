<template>
  <section class="section-projects__wrapper pa-10" id="section-projects">
    <v-container>
      <v-row justify="center">
        <h1 class="text-h1 mb-10" uppercased>Projects</h1>
      </v-row>
      <v-row justify="center" class="mb-10 ">
        <v-col v-for="(project, i) in projects" :key="i" cols="12" md="8">
          <v-card
            v-scrollanimation
            elevation="10"
            color="#14213d"
            dark
            class="mb-5"
          >
            <v-system-bar lights-out></v-system-bar>
            <v-carousel
              reverse-transition="fade-transition"
              transition="fade-transition"
              height="300"
            >
              <v-carousel-item
                v-for="(image, i) in project.images"
                :key="i"
                :src="require(`@/assets/project-slides/${image}`)"
              ></v-carousel-item>
            </v-carousel>
            <v-card-title class="text-h4">
              {{ project.name }}
            </v-card-title>
            <v-card-subtitle>
              {{ project.stack }}
            </v-card-subtitle>
            <v-card-text>
              {{ project.text }}
            </v-card-text>
            <v-card-actions>
              <v-row class="justify-center">
                <v-btn
                  color="#169873"
                  class="ma-2"
                  outlined
                  :href="project.code"
                  target="_blank"
                  v-if="project.code"
                >
                  Code
                </v-btn>
                <v-btn
                  color="#169873"
                  class="ma-2"
                  outlined
                  :href="project.website"
                  target="_blank"
                >
                  Website
                </v-btn>
              </v-row>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  name: "SectionProjects",
  data: function() {
    return {
      projects: [
        {
          name: "Cinemify",
          stack: "Vue.js / SCSS / Axios / REST API",
          text:
            "Single page app made in Vue.js to practice my skills in this framework. You can search here for details about all famous movies. It uploads data from OMDb API by Axios. Styles applied in SCSS.",
          code: "https://github.com/jarobober/cinemify",
          website: "https://infallible-wright-0ae4b6.netlify.app/",
          images: [
            "cinemify/cinemify.png",
            "cinemify/cinemify1.png",
            "cinemify/cinemify2.png"
          ]
        },
        {
          name: "Casa de Papel Quiz",
          stack: "HTML5 / CSS3 / JavaScript",
          text:
            "Single page app quiz made in vanilla JavaScript to practice my programming skills in this language. Markup and styling made in HTML5 and CSS3. Taking part in this quiz you can get to know which character from famous Netflix series 'Casa de Papel' suits your personality.",
          code: "https://github.com/jarobober/quiz",
          website: "https://jarobober.github.io/quiz/",
          images: [
            "casa/casaquiz.png",
            "casa/casaquiz1.png",
            "casa/casaquiz2.png"
          ]
        },
        {
          name: "My friend's portfolio website",
          stack: "HTML5 / CSS3 / JavaScript",
          text:
            "Portfolio website designed and coded for my friend.  Made in HTML5 for markup, CSS3 for styles and JavaScript.",
          code: "https://github.com/jarobober/emil",
          website: "https://jarobober.github.io/emil/",
          images: [
            "emil/emil.png",
            "emil/emil1.png",
            "emil/emil2.png",
            "emil/emil3.png"
          ]
        },
        {
          name: "My travel blog",
          stack: "HTML5 / CSS3 / jQuery / WordPress",
          text:
            "A WordPress theme made fully by myself. Although no previous PHP experience I coded theme using documentation and tutorials found in web. Stack I have chosen for this project was HTML5, CSS3, jQuery and PHP back-end thanks to documentation.",
          code: "",
          website: "https://karoijaro.pl/",
          images: [
            "blog/blog.png",
            "blog/blog1.png",
            "blog/blog2.png",
            "blog/blog3.png"
          ]
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.before-enter {
  opacity: 0;
  transform: scale(0.7) rotateZ(-15deg);
  transition: all 0.5s ease-out;
}

.enter {
  opacity: 1;
  transform: scale(1) rotateZ(0);
  transform: translateY(0px);
}
</style>
