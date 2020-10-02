<template>
  <v-sheet
    max-width="50rem"
    class="d-flex flex-row mx-auto my-10"
    max-height="30rem"
  >
    <v-card max-width="45%" class="ma-4" dir="ltr" outlined>
      <v-card-title class="mb-10"> Ways to reach me: </v-card-title>
      <v-card-text>
        <strong>
          <v-icon>mdi-telegram</v-icon>
          Telegram:
        </strong>
        <a href="https://t.me/Mkh_Pouya"> @Mkh_Pouya </a>
      </v-card-text>

      <v-card-text>
        <strong>
          <v-icon>mdi-gmail</v-icon>
          Email:
        </strong>
        <a href="p.mohammadkhani95@gmail.com">
          <!-- P.Mohammadkhani95 [at] gmail.com -->
          P.Mohammadkhani95 <v-icon dense small>mdi-at</v-icon> gmail.com
        </a>
      </v-card-text>
    </v-card>

    <v-card max-width="45%" class="ma-4" dir="ltr" outlined>
      <v-img aspect-ratio="2.1" src="/Images/Pouya.jpg"> </v-img>
      <v-card-title> Pouya Mohammadkhani </v-card-title>
      <v-card-subtitle>
        <strong>Computer Engineering</strong> from
        <strong>Shahid Beheshti University</strong>
      </v-card-subtitle>
      <v-card-text>
        Welcome to my personal page, I hope you enjoy my works.
      </v-card-text>
    </v-card>
  </v-sheet>
</template>

<script>
export default {};
</script>

<style>
</style>