<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6" class="pa-0">
      <v-progress-linear
        v-model="valueDeterminate"
        fixed
        color="primary"
        height="5"
      ></v-progress-linear>
      <v-stepper v-model="stepper" elevation="0">
        <v-stepper-content step="1" class="pa-2">
          <PlaceAccomodate />
        </v-stepper-content>
        <v-stepper-content step="2" class="pa-2">
          <place-location />
        </v-stepper-content>
        <v-stepper-content step="3" class="pa-2">
          <place-amenities />
        </v-stepper-content>
      </v-stepper>
    </v-col>

    <v-footer :absolute="fixed" app color="white">
      <v-progress-linear
        absolute
        top
        color="secondary"
        height="1"
      ></v-progress-linear>
      <v-row class="pa-6" justify="space-between">
        <v-btn color="primary" text @click="prevStep">
          <v-icon left> mdi-chevron-right </v-icon>
          Back
        </v-btn>
        <v-btn color="primary" @click="nextStep" v-show="!stepperDone"> Next </v-btn>
        <v-btn color="primary" @click="nextStep" v-show="stepperDone"> Finnish </v-btn>
      </v-row>
    </v-footer>
  </v-row>
</template>

<script>
export default {
  name: "PlacePage",
  data() {
    return {
      valueDeterminate: 30,
      stepper: 1,
      fixed: false,
      lastStep: 3,
      stepperDone: false
    };
  },
  methods: {
    nextStep() {
      this.stepper = this.stepper + 1;
      if (this.stepper === this.lastStep) {
        this.valueDeterminate = 100;
        this.stepperDone = true;
      } else if (this.stepper > this.lastStep) {
        this.stepper = this.lastStep;
      } else {
        this.valueDeterminate = this.valueDeterminate + 30;
      }
    },
    prevStep() {
      this.stepper = this.stepper - 1;
      this.stepperDone = false;
      if (this.stepper === 1) {
        this.valueDeterminate = 30;
      } else if (this.stepper < 1) {
        this.stepper = 1;
        this.valueDeterminate = 30;
      } else {
        this.valueDeterminate = this.valueDeterminate - 30;
      }
    },
  },
};
</script>
