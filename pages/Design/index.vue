<template>
  <v-sheet max-width="40rem" class="mx-auto mt-sm-10">
    <v-card>
      <v-card-title> 🚽 🎨 👷 🚧</v-card-title>
      <v-card-text> This page is under construction... </v-card-text>
    </v-card>
    <v-card v-for="pic in pictures" :key="pic.title" class="my-4">
      <!-- <v-img :src="pic.img"></v-img> -->
      <v-card-title> {{ pic.title }} </v-card-title>
      <v-card-text>
        <v-rating :value="pic.stars" color="amber" dense half-increments readonly size="14">
        </v-rating>
        <div class="grey--text">More detail about the picture</div>
      </v-card-text>
    </v-card>
  </v-sheet>
</template> 

<script>
export default {
  data() {
    return {
      pictures: [
        { title: "Picture 1", img: "/Images/Pouya.jpg", stars: 4.5 },
        { title: "Picture 2", img: "/Images/Pouya.jpg", stars: 2.5 },
        { title: "Picture 3", img: "/Images/Pouya.jpg", stars: 3 },
      ],
    };
  },
};
</script>

<style>
</style>