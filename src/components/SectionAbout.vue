<template>
  <section class="section-about__wrapper pa-10" id="section-about">
    <v-container>
      <v-row justify="center">
        <h1 class="text-h2 text-md-h1 pa-2 mb-10" uppercased>About me</h1>
      </v-row>
      <v-row justify="center" class="flex-wrap">
        <v-col cols="12" sm="6" class="mb-4">
          <v-img class="my-photo rounded" src="@/assets/me1.jpg" />
        </v-col>
        <v-col cols="12" sm="6" align-self="center">
          <p v-scrollanimation>
            Although starting my career in a different sector I have got to know
            more about front-end development 2 years ago and I realized that I
            want to choose this path.
          </p>
          <p v-scrollanimation>
            Since then, I have been self-learning, completed several online courses
            and done some non-profit projects for me or my friends. I'm looking
            forward to gain knowledge to be able providing better solutions.
          </p>
          <p v-scrollanimation>
            Beside work, I'm keen traveler looking for adventures in nature. I
            love hiking in the mountains but when I'm close to the ocean never
            hesitate to progress my surfing skills.
          </p>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  name: "SectionAbout"
};
</script>

<style lang="scss" scoped>
.section-about__wrapper {
  background-color: #14213d;
  color: #fff;
}

h1 {
  opacity: 0.8;
}

p {
  opacity: 0.8;
}

.my-photo {
  position: relative;
  height: 400px;
  width: 400px;
}

.my-photo::after {
  position: absolute;
  content: "";
  top: 5%;
  left: 0;
  height: 100%;
  width: 20%;
  background-image: linear-gradient(180deg, #169873 10%, #ffffff00 10%, #ffffff00 20%, #169873 20%, #169873 30%, #ffffff00 30%, #ffffff00 40%, #169873 40%, #169873 50%, #ffffff00 50%, #ffffff00 60%, #169873 60%, #169873 70%, #ffffff00 70%, #ffffff00 80%, #169873 80%, #169873 90%, #ffffff00 90%, #ffffff00 100%);
}

.before-enter {
  opacity: 0;
  transform: translateX(100px);
  transition: all 1s ease;
}

.enter {
  opacity: 1;
  transform: translateX(0);
}

</style>
