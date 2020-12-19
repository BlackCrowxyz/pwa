<template>
    <div id="Educations">
        <h3 class="pb-3">
            <v-icon>mdi-book-account</v-icon>
            Educations
        </h3>
        <template v-for="item in educations">
            <div class="d-flex justify-space-between pr-3" :key="item.title">
                <v-icon size="15">{{ item.icon }}</v-icon>
                <span class="pl-2">{{ item.title }}</span>
                <span class="ml-auto">{{ item.period }}</span>
            </div>
        </template>
    </div>
</template>

<script>
export default {
    data() {
        return {
            educations: [
                {
                    icon: "mdi-school",
                    title: "University of Shahid Beheshti",
                    period: "Sep 2016 - Sep 2020"
                },
                {
                    icon: "mdi-book-open-page-variant",
                    title: "Allameh-tababaiee",
                    period: "2014 - 2016"
                }
            ]
        };
    }
};
</script>

<style lang="scss"></style>
