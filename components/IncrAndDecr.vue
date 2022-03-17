<template>
  <v-card-text class="text--primary d-flex align-center">
    <div class="text-subtitle-1 mr-5">{{ title }}</div>
    <div class="d-flex align-center">
      <v-btn
        class="mx-3"
        id="custom-disabled"
        fab
        dark
        x-small
        outlined
        color="primary"
        @click="prev"
        :disabled="size === 1"
      >
        <v-icon dark> mdi-minus </v-icon>
      </v-btn>
      <div style="width: 30px" class="text-center">{{ size }}</div>
      <v-btn
        class="mx-3"
        fab
        dark
        x-small
        outlined
        color="primary"
        @click="next"
      >
        <v-icon dark> mdi-plus </v-icon>
      </v-btn>
    </div>
  </v-card-text>
</template>

<script>
export default {
  name: "PlaceAccomodateIncrAndDecr",
  props: ["title", "size"],
  methods: {
    next() {
      this.size = this.size + 1;
    },
    prev() {
      this.size = this.size - 1;
      if (this.size < 1) {
        this.size = 1;
      }
    },
  },
};
</script>

<style lang="scss">
.accomodate {
  #custom-disabled.v-btn--disabled {
    border-color: silver !important;
  }
}
</style>
