<template>
    <section id="summary">
        <v-container rounded class="deep-purple lighten-4">
            <v-row id="summary" no-gutters>
                <v-col class="col-xl-12 col-sm-4">
                    <div class="d-flex justify-center">
                        <v-avatar class="profile ma-8">
                            <img src="~/static/Images/Profile.jpg" alt="alt" />
                        </v-avatar>
                    </div>
                </v-col>
                <v-col class="col-sm-8">
                    <div class="mt-10 my-5 px-5">
                        <h1>Pouya Mohammadkhani</h1>
                        <p class="grey--text text--darken-1">
                            I'm a frontend developer
                        </p>
                        <p>Hi there ..</p>
                    </div>
                </v-col>
            </v-row>
            <v-divider></v-divider>
            <v-row
                id="contact"
                class="d-flex justify-space-between pa-5 px-10"
                no-gutters
            >
                <template v-for="item in contact">
                    <div
                        class="d-flex justify-space-around pb-2"
                        :key="item.text"
                    >
                        <v-icon class=" pr-1">{{ item.icon }}</v-icon>
                        <span v-if="item.link">
                            <a :href="item.link">
                                {{ item.text }}
                            </a>
                        </span>
                        <span v-else>{{ item.text }}</span>
                    </div>
                </template>
            </v-row>
        </v-container>
    </section>
</template>

<script>
export default {};
</script>

<script>
export default {
    data() {
        return {
            contact: [
                {
                    icon: "mdi-gmail",
                    text: "Email",
                    link: "p.mohammadkhani95@gmail.com"
                },
                {
                    icon: "mdi-github",
                    text: "Github",
                    link: "https://github.com/BlackCrowxyz"
                },
                {
                    icon: "mdi-linkedin",
                    text: "LinkedIn",
                    link:
                        "https://www.linkedin.com/in/pouya-mohammadkhani-8877021b9/"
                },
                {
                    icon: "mdi-whatsapp",
                    text: "+989305387992"
                },
                {
                    icon: "mdi-telegram",
                    text: "@Mkh_Pouya",
                }
            ]
        };
    }
};
</script>

<style lang="scss">
#summary {
    .border {
        border: 2px solid black;
    }
    .profile {
        //Calculate the size of image based on the size of the page
        height: 250px !important;
        min-width: 250px !important;
        width: 250px !important;
    }
}
</style>
