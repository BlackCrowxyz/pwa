<template>
    <div class="mx-auto">
        <MySummary />
        <v-container>
            <v-row no-gutters>
                <v-col class="col-xl-12 col-6">
                    <Educations />
                </v-col>
            </v-row>
            <v-row no-gutters>
                <v-col class="col-xl-12 col-6">
                    <ProgrammingSkills />
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
import MySummary from "@/components/Sections/mySummary.vue";
import Educations from "@/components/Sections/Educations.vue";
import ProgrammingSkills from "@/components/Sections/ProgrammingSkills.vue";
export default {
    components: { MySummary, Educations, ProgrammingSkills }
};
</script>

<style lang="scss"></style>
