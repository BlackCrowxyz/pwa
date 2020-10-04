<template>
  <div  class="mx-auto">
    <v-card outlined rounded>
      <v-card-title> Pouya Mohammadkhani </v-card-title>
      <v-card-subtitle> My personal webpage </v-card-subtitle>
      <v-card-text class="py-3">
        Welcome to my personal website. I am a Front-end developer.
      </v-card-text>
      <v-divider inset></v-divider>
      <v-card-text class="py-3">
        Feel free to visit my website and other tabs for more information.
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import VuetifyLogo from "~/components/VuetifyLogo.vue";

export default {
  components: {
    Logo,
    VuetifyLogo,
  },
};
</script>
