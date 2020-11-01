<template>
  <v-sheet
    class="d-flex flex-column mx-auto mt-sm-10 white--text"
    color="deep-purple"
    max-width="40rem"
    rounded
  >
    <!-- <div
      v-anime="{
        rotate: '1turn',
        backgroundColor: '#FFF',
        duration: 2000,
        loop: true
      }"
    >
      <p class="yellow">Hello</p>
    </div> -->

    <div @click="call()" class="my-item">
      <div id="emoji">😆😂</div>
      
      <svg id="demo-svg" width="400" height="700">
        <path
          stroke="red"
          fill="none"
          d="M 560 320 L 420 240 L 460 160 L 120 140 L 220 220 L 100 340 L 340 300 L 320 400 L 60 400 L 380 460 L 560 480 L 720 380 "
        ></path>
      </svg>
    </div>

    <!-- Add to works -->
    <!-- <v-card class="d-flex justify-center" color="primary" outlined>
      <v-card-actions>
        <v-btn depressed small color="amber" @click="updateLayout('edit')"
          >ویرایش لیست</v-btn
        >
        <v-btn depressed small color="amber" @click="updateLayout('new-item')"
          >افزودن مورد جدید</v-btn
        >
      </v-card-actions>
    </v-card> -->
    <!-- <v-card v-show="isNewItem" color="yellow darken-1" outlined>
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
    </v-card> -->
    <!-- Works -->
    <!-- <v-card color="deep-purple" outlined> -->
    <!-- <v-card-text class=""> -->

    <!-- <v-timeline align-top dense>
      <v-timeline-item
        v-for="item in works"
        :key="item.title"
        color="pink"
        small
      >
        <v-row no-gutters>
          <v-col cols="12">
            <strong v-text="item.time" />
          </v-col>
          <v-col cols="12"> 
            <span class="text-caption" v-text="item.text" />
          </v-col>
           
        </v-row> 
      </v-timeline-item>
    </v-timeline> -->

    <!-- <v-speed-dial
      v-model="fab"
      bottom
      right
      dark
      direction="top"
      open-on-hover
      transition="slide-y-reverse-transition"
      fixed
    >
      <template #activator>
        <v-btn v-model="fab" class="mb-16" color="red" dark fab
          ><v-icon v-if="!fab">mdi-plus</v-icon
          ><v-icon v-else>mdi-close</v-icon></v-btn
        >
      </template>
      <v-btn
        v-for="btn in dialBtns"
        :color="btn.color"
        :key="btn.icon"
        @click="btn.func"
        dark
        fab
        small
        ><v-icon>{{ btn.icon }}</v-icon></v-btn
      >
    </v-speed-dial> -->

    <v-dialog
      v-model="dialog"
      persistent
      :overlay="false"
      max-width="20rem"
      transition="dialog-transition"
    >
      <v-card>
        <v-card-title class="text-body-1">
          Add new item to timeline
        </v-card-title>
        <v-card-text>
          <div class="d-flex flex-column">
            <v-card-subtitle>Time</v-card-subtitle>
            <v-text-field
              v-model="time"
              :rules="[rules.required, rules.number]"
              dense
              outlined
              required
            ></v-text-field>
            <v-card-subtitle>Title</v-card-subtitle>
            <v-text-field
              v-model="text"
              :rules="[rules.required]"
              dense
              outlined
              required
            ></v-text-field>
            <v-card-actions class="pa-0">
              <v-btn block depressed dark color="amber" @click="addToWorks"
                >Add</v-btn
              >
            </v-card-actions>
          </div>
        </v-card-text>
      </v-card>
    </v-dialog>
    <v-snackbar v-model="snackbar" timeout="4000">
      New item added !
      <template v-slot:action="{ attrs }">
        <v-btn color="yellow" text v-bind="attrs" @click="snackbar = false">
          Close
        </v-btn>
      </template>
    </v-snackbar>
    <!-- </v-card-text> -->
    <!-- </v-card> -->
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      snackbar: false,
      dialog: false,
      fab: false,
      dialBtns: [
        // { icon: "mdi-pencil", color: "green", func: this.AddItem },
        // { icon: "mdi-delete", color: "red", func: this.AddItem },
        { icon: "mdi-plus", color: "amber", func: this.AddItem }
      ],
      works: [
        { time: "2020", text: "🏢 HiMart Company" },
        { time: "2020", text: "👨‍🎓 Graduated from Shahid Beheshti University" },
        { time: "2019", text: "🧑‍🎓 IPM" },
        { time: "2018", text: "🎉 Front-end Developement" },
        { time: "2016", text: "🤩 Entering University" },
        { time: "2016", text: "✔️ Konkoor" },
        { time: "2016", text: "✔️ Konkoor" },
        { time: "2016", text: "✔️ Konkoor" },
        { time: "2016", text: "✔️ Konkoor" }
      ],
      time: "",
      text: "",
      rules: {
        required: value => !!value || "Can't be empty",
        number: value => {
          const pattern = /^.[0-9]{0,3}$/;
          return pattern.test(value) || "Just numbers";
        }
      }
    };
  },
  computed: {
    content() {
      return this.isEdit;
    }
  },
  methods: {
    AddItem() {
      console.log("Add clicked");
      this.dialog = true;
    },
    addToWorks() {
      this.works.unshift({
        time: this.time,
        text: this.text
      });
      this.dialog = false;
      this.snackbar = true;
    },
    call() {
      let targets = "#mi";
      this.$anime
        .timeline()
        .add({
          targets,
          translateX: 250,
          easing: "easeOutExpo"
        })
        .add({
          targets,
          translateX: 250,
          easing: "easeOutExpo"
        });
      let path = this.$anime.path("#demo-svg path");
      this.$anime({
        targets: "#emoji",
        translateX: path("x"),
        translateY: path("y"),
        easing: "linear",
        duration: "4000"
      });
    }
  }
};
</script>

<style>
.hide-scroll {
  overflow: hidden !important;
}
</style>
