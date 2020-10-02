<template>
  <!-- <v-sheet class="d-flex flex-column" max-height="30rem"> -->
  <v-sheet
    max-width="50rem"
    class="d-flex flex-column mx-auto my-10"
    max-height="30rem"
  >
    <!-- Add to works -->
    <v-card class="d-flex justify-center" color="primary" outlined>
      <v-card-actions>
        <v-btn depressed small color="amber" @click="updateLayout('edit')"
          >ویرایش لیست</v-btn
        >
        <v-btn depressed small color="amber" @click="updateLayout('new-item')"
          >افزودن مورد جدید</v-btn
        >
      </v-card-actions>
    </v-card>
    <v-card v-show="isNewItem" class="mt-5" color="yellow darken-1" outlined>
      <v-card-title class="mx-auto">افزودن مورد جدید</v-card-title>
      <v-card-subtitle class="mx-auto"
        >زمان و موضوع مورد جدید را وارد کنید</v-card-subtitle
      >
      <v-card-actions class="align-content-end">
        <v-text-field
          v-model="time"
          :rules="[rules.required, rules.number]"
          class="ma-3"
          outlined
          label="زمان"
        />
        <v-text-field
          v-model="title"
          :rules="[rules.required]"
          class="ma-3"
          outlined
          label="تیتر"
        />
        <v-text-field
          v-model="text"
          :rules="[rules.required]"
          class="ma-3"
          outlined
          label="متن"
        />

        <v-btn class="mb-10 ma-3" color="success" @click="addToWorks"
          >اضافه کن</v-btn
        >
      </v-card-actions>
    </v-card>
    <!-- Works -->
    <v-card class="mt-5" color="deep-purple" outlined>
      <v-card-text class="white--text">
        <v-timeline align-top dense>
          <v-timeline-item
            v-for="(item, i) in works"
            :key="i"
            color="pink"
            small
          >
            <v-row class="pt-1 pl-8">
              <v-col cols="2">
                <strong v-text="item.time" />
              </v-col>
              <v-col class="ml-6">
                <strong v-text="item.title" />
                <div class="caption" v-text="item.text" />
              </v-col>
              <v-col v-show="isEdit" sm="1" class="ma-1">
                <v-btn depressed small color="deep-orange">ویرایش</v-btn>
              </v-col>
              <v-col v-show="isEdit" sm="1" class="ma-1">
                <v-btn depressed small color="yellow">حذف</v-btn>
              </v-col>
            </v-row>
            <v-divider></v-divider>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-card>
    <v-card class="mt-16">
      <!-- TODO -->
      trailing box !!!
    </v-card>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      isEdit: false,
      isNewItem: false,
      works: [
        { title: "1", time: "2019", text: "Lorem ipsun" },
        { title: "2", time: "2018", text: "Lorem ipsun" },
        { title: "2", time: "2018", text: "Lorem ipsun" },
        { title: "2", time: "2018", text: "Lorem ipsun" },
        { title: "2", time: "2018", text: "Lorem ipsun" },
        { title: "2", time: "2018", text: "Lorem ipsun" },
      ],

      time: "",
      title: "",
      text: "",
      rules: {
        required: (value) => !!value || "نمی‌تونه خالی باشه",
        number: (value) => {
          const pattern = /^.[0-9]{0,3}$/;
          return pattern.test(value) || "فقط عدد وارد کنید";
        },
      },
    };
  },
  computed: {
    content() {
      return this.isEdit;
    },
  },
  methods: {
    addToWorks() {
      this.works.unshift({
        time: this.time,
        title: this.title,
        text: this.text,
      });
    },
    updateLayout(cmd) {
      if (cmd == "new-item") {
        this.isNewItem = !this.isNewItem;
        this.isEdit = false;
      } else if (cmd == "edit") {
        this.isEdit = !this.isEdit;
        this.isNewItem = false;
      }
    },
  },
};
</script>

<style>
.hide-scroll {
  overflow: hidden !important;
}
</style>