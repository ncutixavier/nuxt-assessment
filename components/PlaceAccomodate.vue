<template>
  <v-card flat class="accomodate">
    <v-card-title class="h5">
      How many guests your place can you accomodate?
    </v-card-title>
    <v-card-text>
      <div class="text--secondary text-body-1">
        Check that you have enough beds to accomodate all your guests
        comfortably.
      </div>
    </v-card-text>

    <incr-and-decr :title="'Guests'" :size="guests" />

    <div class="px-4 mt-5">
      <div class="text--secondary text-body-1">
        How many bedrooms can guests use?
        <v-select
          :items="rooms"
          dense
          outlined
          class="mt-2"
          style="width: 70%;"
        ></v-select>
      </div>
    </div>

    <incr-and-decr :title="'Beds'" :size="beds" />

    <div class="px-4 mt-2">
      <div class="headline mb-2">Sleeping arrangements</div>
      <div>
        Sharing the types of beds in each room can help people understand the
        sleeping arrangements
      </div>
    </div>
  </v-card>
</template>

<script>
import IncrAndDecr from "./IncrAndDecr.vue";
export default {
  components: { IncrAndDecr },
  name: "PlaceAccomodate",
  data() {
    return {
      guests: 10,
      disabled: false,
      rooms: [
        { text: "Studio", value: "Studio" },
        { text: "1 Bedroom", value: "1 Bedroom" },
        { text: "2 Bedrooms", value: "2 Bedrooms" },
        { text: "3 Bedrooms", value: "3 Bedrooms" },
        { text: "4 Bedrooms", value: "4 Bedrooms" },
      ],
      beds: 1,
    };
  },
  methods: {
    next() {
      this.guests = this.guests + 1;
    },
    prev() {
      this.guests = this.guests - 1;
      if (this.guests < 1) {
        this.guests = 1;
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
