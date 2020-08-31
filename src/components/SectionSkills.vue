<template>
  <section class="section-skills__wrapper pa-10" id="section-skills">
    <v-container>
      <v-row justify="center">
        <h1 class="text-h2 text-md-h1 pa-2 mb-10" uppercased>Skills</h1>
      </v-row>
      <v-row justify="center">
        <v-col cols="12" md="6" lg="4" v-for="item in skills" :key="item.name">
          <v-card
            v-scrollanimation
            class="my-5 mx-auto pt-2 rounded"
            elevation="5"
            width="300"
            height="350"
            tile
          >
            <v-img
              :src="require(`@/assets/skills/${item.img}`)"
              class="mx-auto"
              height="100"
              contain
              :alt="item.title"
            />
            <v-card-title>
              {{ item.title }}
            </v-card-title>
            <v-card-subtitle>
              {{ item.subtitle }}
            </v-card-subtitle>
            <v-card-text>
              {{ item.text }}
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  name: "SectionSkills",
  data: function() {
    return {
      skills: [
        {
          title: "Vue.js",
          subtitle: "Vue CLI / Vue Router / Vuetify",
          text:
            "I'm able to create Vue CLI projects, creating routes with Vue Router, creating Components, custom Directives and using Vuetify if there is a need for UI framework.",
          img: "logo.png"
        },
        {
          title: "JavaScript",
          subtitle: "JavaScipt ES5/ES6+",
          text:
            "I know how Object-oriented Programming and asynchronous operations work. I can manipulate DOM API using JS or make algorithms to manage data. I try to update my knowledge with current ES versions.",
          img: "js-logo.png"
        },
        {
          title: "HTML 5",
          subtitle: "HyperText Markup Language",
          text:
            "I pay attention to write semantically correct code what helps Search Engine Optimalization and accessibility.",
          img: "html-logo.png"
        },
        {
          title: "CSS 3",
          subtitle: "Grid / Flexbox / Pseudoclasses",
          text:
            "I'm able to code layouts using grid and flexbox. I know how to use pseudoclasses and make animations using keyframes. Mobile-first approach.",
          img: "css-logo.png"
        },
        {
          title: "SASS / SCSS",
          subtitle: "CSS Preprocessors",
          text:
            "I know how to use variables, nested classes and mixins. In my projects I usually use SCSS.",
          img: "sass-logo.png"
        },
        {
          title: "Git",
          subtitle: "GitHub repository",
          text:
            "I use Git on command line. So far I was using it for projects made only by myself, so I would like to learn the workflow in a team.",
          img: "github-logo.png"
        },
        {
          title: "Axios",
          subtitle: "REST API queries",
          text:
            "To fetch data from REST API in my Vue.js projects I take advantage of Axios.",
          img: "axios.jpg"
        },
        {
          title: "WordPress",
          subtitle: "CMS",
          text:
            "My fascination about front-end started from WordPress. Firstly I made few websites using free themes and after gaining some HTML/CSS/JS skills I built my own theme for a travel blog.",
          img: "wordpress-logo.png"
        },
        {
          title: "English",
          subtitle: "B2 level / fluent spoken and written",
          text:
            "I'm able to communicate fluently in spoken and written English. I used to work in Scotland serving English-speaking customers and cooperating in multinational team. Usage of English documentation is not a problem for me.",
          img: "british-flag.png"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.section-skills__wrapper {
  background-color: #e5e5e5;
}

.before-enter {
  opacity: 0;
  transform: translateY(100px);
  transition: all 1s ease-out;
}

.enter {
  opacity: 1;
  transform: translateY(0);
}
</style>
