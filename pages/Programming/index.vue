<template>
  <v-sheet max-width="50rem" class="d-flex flex-column mx-auto my-10">
    <v-card outlined color="amber darken-1">
      <v-card-title primary-title>
        <v-icon right>mdi-file-account</v-icon>
        Resume
      </v-card-title>
    </v-card>
    <div>
      <v-card outlined class="mt-3" color="amber lighten-1">
        <v-list>
          <v-list-group
            v-for="item in items"
            :key="item.title"
            v-model="item.active"
            :prepend-icon="item.action"
            no-action
          >
            <template v-slot:activator>
              <v-list-item-content>
                <v-list-item-title
                  class="ml-2"
                  v-text="item.title"
                ></v-list-item-title>
              </v-list-item-content>
            </template>

            <v-list-item v-for="child in item.items" :key="child.title">
              <v-list-item-content>
                <v-list-item-title class="pb-4 pt-8 px-5 ml-16">
                  <v-slider
                    dir="ltr"
                    v-model="child.val"
                    :prepend-icon="child.icon"
                    :label="child.title"
                    step="1"
                    max="5"
                    thumb-label="always"
                    thumb-size="24"
                    readonly
                    ticks
                    dense
                    hide-details
                  ></v-slider>
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list-group>
        </v-list>
      </v-card>
    </div>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          action: "mdi-xml",
          active: true,
          items: [
            { title: "C/C++", icon: "mdi-language-cpp", val: 4 },
            { title: "Java", icon: "mdi-language-java", val: 3 },
            { title: "Python", icon: "mdi-language-python", val: 3 },
            { title: "JavaScript", icon: "mdi-language-javascript", val: 4 },
            { title: "CSS", icon: "mdi-language-css3", val: 5 },
            { title: "HTML", icon: "mdi-language-html5", val: 4 },
          ],
          title: "Programming Languages",
        },
        {
          action: "mdi-briefcase",
          items: [{ title: "IPM" }, { title: "Himart" }, { title: "?" }],
          title: "Work Experience",
        },
      ],
    };
  },
};
</script>

<style>
</style>