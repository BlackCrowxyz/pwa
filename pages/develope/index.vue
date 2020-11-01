<template>
  <v-sheet trans max-width="40rem" class="d-flex flex-column mx-auto mt-sm-10">
    <v-card class="mb-2" outlined :color="`${$color} darken-1`" dark>
      <v-card-title>
        <v-icon left>mdi-file-account</v-icon>
        Resume
      </v-card-title>
    </v-card>
    <span class="mt-6"></span>

    <article class="education">
      <!-- <v-subheader>
        Skills
      </v-subheader> -->
      <div class="my-2 text-h6">
        <span
          :class="`${$color}--text`"
          style="position: relative;
    left: 5px;"
          >Edu</span
        >
        cation
      </div>
      <v-card outlined>
        <section>
          <!-- <v-subheader>23 rf3 </v-subheader> -->

          <!-- <v-card-title>1 341234 1</v-card-title>
          <v-card-text>awefawef</v-card-text>
          <v-card-subtitle>awefawef</v-card-subtitle> -->
          <template v-for="edu in educations">
            <div
              class="d-flex justify-center justify-space-between ma-3"
              :key="edu.title"
            >
              <span class="year font-weight-medium my-auto">{{
                edu.year
              }}</span>
              <span
                class="title text-body-1 font-weight-bold my-auto ml-4"
                >{{ edu.title }}</span
              >
              <span
                class="italic text-caption font-italic  my-auto ml-auto mr-3"
                >{{ edu.month }}</span
              >
            </div>
          </template>
        </section>
      </v-card>
    </article>
    <!-- <v-divider class="mt-6"></v-divider> -->
    <span class="mt-6"></span>
    <section class="skills">
      <!-- <v-subheader>
        Skills
      </v-subheader> -->
      <div class="my-2 text-h6">
        <span
          :class="`${$color}--text`"
          style="position: relative;
    left: 5px;"
          >Ski</span
        >
        lls
      </div>
      <v-card outlined>
        <!-- :color="`${$color} lighten-1`" -->
        <v-list flat dense>
          <v-list-group
            v-for="item in items"
            :key="item.title"
            :prepend-icon="item.action"
            no-action
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title
                  class="text-body-2"
                  v-text="item.title"
                ></v-list-item-title>
              </v-list-item-content>
            </template>

            <v-list-item
              v-for="child in item.items"
              :key="child.title"
              class="px-4"
            >
              <v-list-item-content>
                <v-list-item-title class="d-flex align-center">
                  <v-icon class="px-1">{{ child.icon }}</v-icon>
                  <span class="px-1">{{ child.title }}</span>
                  <v-progress-linear
                    class="px-1"
                    :value="child.val"
                    rounded
                  ></v-progress-linear>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
        </v-list>
      </v-card>
    </section>
    <v-divider class="mt-6"></v-divider>
    <section>
      <div class="my-2  text-h6">
        <span
          :class="`${$color}--text`"
          style="position: relative;
    left: 5px;"
          >Pro</span
        >
        gramming
      </div>
      <v-card
        outlined
        class="d-flex justify-center justify-space-around flex-wrap pa-3"
      >
        <!-- :style="`border:0px solid ${$color};`" -->
        <template v-for="skill in skills">
          <div
            class="d-flex flex-column justify-center mx-4"
            :key="skill.title"
          >
            <v-progress-circular
              class="mx-auto mb-auto text-truncate"
              :value="skill.value"
              :color="$color"
              :size="100"
              :width="12"
            >
              {{ skill.title }}</v-progress-circular
            >
            <span
              class="text-center font-weight-light my-2"
              style="max-width:140px"
              >{{ skill.subtitle }}</span
            >
          </div>
        </template>

        <!-- <div class="d-flex flex-column justify-center ">
          <v-progress-circular
            :value="20"
            color="teal"
            :size="100"
            :width="15"
          >
          Python</v-progress-circular>
          <span class="text-center font-weight-medium my-3">Python</span>
        </div> -->
      </v-card>
    </section>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      // color: "blue",
      educations: [
        {
          year: 2020,
          title: "From university",
          details: "c++, python",
          month: "Februray"
        }
      ],
      skills: [
        {
          title: "HTML 5",
          subtitle: "SEO Optimization",
          value: 40
        },
        {
          title: "CSS 3",
          subtitle: "Structural Programming",
          value: 60
        },
        {
          title: "Js",
          subtitle: "Vuejs Framework",
          value: 80
        },
        {
          title: "Ts",
          subtitle: "Just learning...",
          value: 30
        }
      ],
      items: [
        {
          action: "mdi-xml",
          items: [
            { title: "C/C++", icon: "mdi-language-cpp", val: 80 },
            { title: "Java", icon: "mdi-language-java", val: 60 },
            { title: "Python", icon: "mdi-language-python", val: 70 },
            { title: "JavaScript", icon: "mdi-language-javascript", val: 65 }
          ],
          title: "Languages"
        },
        {
          title: "Front-end",
          action: "mdi-monitor-cellphone-star",
          items: [
            { title: "Vuejs", icon: "mdi-vuejs" },
            { title: "Nuxt", icon: "mdi-nuxt" },
            { title: "Vuetify", icon: "mdi-vuetify" },
            { title: "Vuex", icon: "mdi-vector-union" },
            { title: "JavaScript", icon: "mdi-language-javascript", val: 80 },
            { title: "CSS", icon: "mdi-language-css3", val: 60 },
            { title: "Bootstrap", icon: "mdi-bootstrap", val: 60 },
            { title: "HTML", icon: "mdi-language-html5", val: 90 }
          ]
        },
        {
          action: "mdi-briefcase",
          items: [
            { title: "IPM", icon: "mdi-ip" },
            { title: "Himart", icon: "mdi-hospital-marker" },
            { title: "?" }
          ],
          title: "Work Experience"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.education {
  div {
    span {
      // position: relative;
      // // top: 1rem;
      // &.year {
      //   left: 1rem;
      // }
      // &.title {
      //   left: 3.5rem;
      // }
      // &.italic {
      //   right: 2rem;
      // }
    }
  }
}
</style>
