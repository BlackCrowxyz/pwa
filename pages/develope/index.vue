<template>
  <v-sheet max-width="50rem" class="d-flex flex-column mx-auto">
    <v-card class="my-2" outlined color="amber darken-1" dark>
      <v-card-title>
        <v-icon right>mdi-file-account</v-icon>
        Resume
      </v-card-title>
    </v-card>
    <div>
      <v-card outlined color="amber lighten-1">
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
                <v-list-item-title dir="ltr" class="d-flex align-center">
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
          items: [
            { title: "C/C++", icon: "mdi-language-cpp", val: 80 },
            { title: "Java", icon: "mdi-language-java", val: 60 },
            { title: "Python", icon: "mdi-language-python", val: 70 },
            { title: "JavaScript", icon: "mdi-language-javascript", val: 80 },
            { title: "CSS", icon: "mdi-language-css3", val: 60 },
            { title: "HTML", icon: "mdi-language-html5", val: 90 },
          ],
          title: "Languages",
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