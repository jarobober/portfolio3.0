<template>
  <section class="hero-page__wrapper" id="hero-page">
    <v-container fill-height>
      <v-col align="center">
        <v-row justify="center">
          <h1 class="hero-page__heading">
            Hi, I'm Jaro
            <br /> 
            a front-end developer
          </h1>
        </v-row>
        <v-row cols="12" justify="center">
          <p class="hero-page__subheading my-xs-5 my-sm-10">
            Scroll down to go through all sections or get directly to my ...
          </p>
        </v-row>
        <v-row cols="12" justify="center">
          <v-btn 
            class="ma-3" 
            color="white" 
            outlined
            @click="$vuetify.goTo('#section-skills');"
          >
            skills
          </v-btn>
          <v-btn 
            class="ma-3" 
            color="#169873" 
            depressed
            @click="$vuetify.goTo('#section-projects');"
          >
            projects
          </v-btn>
        </v-row>
      </v-col>
    </v-container>
  </section>
</template>

<script>
export default {
  name: "HeroPage"
};
</script>

<style lang="scss" scoped>
.hero-page__wrapper {
  top: 0;
  left: 0;
  position: relative;
  background-image: url("../assets/heroimage1.jpg");
  background-size: cover;
  background-position: center;
  height: 100vh;
  z-index: 0;
}

.hero-page__wrapper::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4);
  z-index: -1;
}


.hero-page__heading {
  color: white;
  padding: 10px;
  border-right: 2px solid white;
  text-align: right;
  z-index: 1;

  @media (min-width: 768px) {
    font-size: 54px;
  }
}

.hero-page__subheading {
  color: white;
  font-weight: 300;
  width: 200px;

  @media (min-width: 768px) {
    font-size: 22px;
    width: 400px;
  }
}
</style>
