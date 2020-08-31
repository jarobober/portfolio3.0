<template>
  <v-parallax
    class="section-divider__parallax pt-3"
    src="@/assets/parallax.jpg"
    height="450"
  >
    <v-container>
      <v-row justify="center">
        <v-col
          v-for="(item, i) in practices"
          :key="i"
          v-scrollanimation
          cols="12"
          md="3"
          class="mx-5"
        >
          <v-img
            :src="require(`@/assets/icons/${item.icon}.png`)"
            width="50"
            class="mx-auto"
          />
          <p class="mt-2 mx-auto text-center text-h6">{{ item.text }}</p>
        </v-col>
      </v-row>
    </v-container>
  </v-parallax>
</template>

<script>
export default {
  name: "SectionDivider",
  data: function() {
    return {
      practices: [
        {
          icon: "rwd",
          text: "Mobile-first and responsive web design."
        },
        {
          icon: "accessibility",
          text: "Accessible for all users."
        },
        {
          icon: "learn",
          text: "Never stop learning."
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.section-divider__parallax {
  z-index: 0;
}

.section-divider__parallax::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1;
}

h2 {
  opacity: 0.9;
}

p {
  opacity: 0.7;
}

.before-enter {
  opacity: 0;
  transition: all 1s ease-in;
}

.enter {
  opacity: 1;
}
</style>
