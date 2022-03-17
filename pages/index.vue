<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card flat>
        <v-card-title class="headline">
          Let's get started listing your space
        </v-card-title>
        <v-card-title class="headline">
          What kind of place do you have?
        </v-card-title>
        <v-card-text>
          <v-select
            :items="room_types"
            label="Room Type"
            dense
            outlined
          ></v-select>
          <v-select
            :items="guests"
            label="Guests"
            dense
            outlined
          ></v-select>
          <v-text-field
            label="Address"
            placeholder="Address"
            outlined
            dense
          ></v-text-field>
        </v-card-text>
        <v-card-actions class="px-4">
          <v-btn color="primary" nuxt to="/place"> Continue </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      room_types: [
        { text: "Entire home/apt", value: "Entire home/apt" },
        { text: "Private room", value: "Private room" },
        { text: "Shared room", value: "Shared room" },
      ],
      guests: [
        { text: "1 guest", value: "1 guest" },
        { text: "2 guests", value: "2 guests" },
        { text: "3 guests", value: "3 guests" },
        { text: "4 guests", value: "4 guests" },
        { text: "5 guests", value: "5 guests" },
        { text: "6 guests", value: "6 guests" },
        { text: "7 guests", value: "7 guests" },
        { text: "8 guests", value: "8 guests" },
        { text: "9 guests", value: "9 guests" },
        { text: "10 guests", value: "10 guests" },
      ],
    };
  },
};
</script>
