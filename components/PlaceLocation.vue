<template>
  <v-card flat class="accomodate">
    <v-card-title class="h5"> Where's your place located? </v-card-title>
    <v-card-text>
      <div class="text--secondary text-body-1">
        Guests will only get your exact address once they've booked a
        reservation
      </div>
    </v-card-text>

    <v-card-text>
      <v-btn block color="primary" outlined>
        <v-icon left style="transform: rotate(-45deg)"> mdi-send </v-icon>
        Use current Location
      </v-btn>
    </v-card-text>

    <div class="px-4 d-flex align-center text--secondary">
      <v-divider></v-divider>
      <div class="mx-2">or enter your address</div>
      <v-divider></v-divider>
    </div>

    <div class="px-4 mt-5">
      <div class="text--secondary text-body-1">
        Country/Region
        <v-select
          :items="countries"
          outlined
          class="mt-2"
          v-model="country"
        ></v-select>
      </div>
    </div>

    <div class="px-4">
      <div class="text--secondary text-body-1">
        Street address
        <v-text-field
          placeholder="House name/number + street/road"
          outlined
        ></v-text-field>
      </div>
    </div>

    <div class="px-4">
      <div class="text--secondary text-body-1">
        Apt, suite. (optional)
        <v-text-field
          placeholder="Apt, suite, building access code"
          outlined
        ></v-text-field>
      </div>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "PlaceAccomodate",
  data() {
    return {
      country: "Rwanda",
      countries: [
        { text: "Rwanda", value: "Rwanda" },
        { text: "Uganda", value: "Uganda" },
        { text: "Tanzania", value: "Tanzania" },
        { text: "Kenya", value: "Kenya" },
        { text: "South Africa", value: "South Africa" },
      ],
    };
  },
};
</script>

<style lang="scss"></style>
