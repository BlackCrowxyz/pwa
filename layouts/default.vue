<template>
  <v-app dark>
    <!-- <v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>-->

    <!-- <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>-->

    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <!-- <v-footer class="pa-0" fix app>
      <v-card class="d-flex grow">
        <v-tabs v-model="tab" background-color="deep-purple accent-4" centered dark grow icons-and-text>
          <v-tab v-for="(item, i) in items" :key="i" :to="item.to">
            {{item.title}}
            <v-icon>{{item.icon}}</v-icon>
          </v-tab>
        </v-tabs>
      </v-card>
    </v-footer> -->
    <section class="d-flex justify-center">
      <v-bottom-navigation
        background-color="red"
        color="yellow"
        app
        grow
        shift
        dark
        hide-on-scroll
      >
        <!-- max-width="40rem" -->
        <!-- fixed -->
        <v-btn v-for="item in items" :key="item.title" :to="item.to">
          <span>{{ item.title }}</span>
          <v-icon>{{ item.icon }}</v-icon>
        </v-btn>
      </v-bottom-navigation>
    </section>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      // text:
      //   "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        // {
        //   icon: "mdi-dots-horizontal",
        //   title: "بقیه",
        //   to: "/Other",
        // },
        {
          icon: "mdi-palette",
          title: "Design",
          to: "/design"
        },
        {
          icon: "mdi-home",
          title: "Home",
          to: "/home"
        },
        {
          icon: "mdi-xml",
          title: "Develope",
          to: "/develope"
        },
        {
          icon: "mdi-account-tie",
          title: "About Me",
          to: "/about"
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js"
    };
  }
};
</script>

<style lang="scss">
.v-item-group.v-bottom-navigation--fixed {
  // position: relative;
  border-radius: 25px 25px 0 0;
}
</style>
