<template>
  <v-card flat class="accomodate">
    <v-card-title class="h5"> What amenities do you offer? </v-card-title>
    <v-card-text>
      <div class="text--secondary text-body-1">
        These are just the amenities guests usually expect, but you can add even
        more after you publish.
      </div>
    </v-card-text>

    <v-card-text>
      <v-list two-line flat>
        <v-list-item-group>
          <template v-for="(item, index) in items">
            <v-list-item :key="item.title" class="pa-0">
              <v-list-item-content>
                <v-list-item-subtitle
                  class="text--primary"
                  v-text="item.headline"
                ></v-list-item-subtitle>

                <v-list-item-subtitle
                  v-text="item.subtitle"
                ></v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-action>
                <v-btn
                  class="mx-2"
                  fab
                  dark
                  x-small
                  color="secondary"
                  elevation="3"
                >
                  <v-icon dark> </v-icon>
                </v-btn>
              </v-list-item-action>
            </v-list-item>

            <v-divider v-if="index < items.length - 1" :key="index"></v-divider>
          </template>
        </v-list-item-group>
      </v-list>
    </v-card-text>
  </v-card>
</template>

<script>
import IncrAndDecr from "./IncrAndDecr.vue";
export default {
  components: { IncrAndDecr },
  name: "PlaceAccomodate",
  data() {
    return {
      items: [
        {
          headline: "Essentials",
          subtitle: `Towers, bed sheets, soap, toilet paper, and pillows`,
        },
        {
          headline: "Wifi",
          subtitle: ``,
        },
        {
          headline: "TV",
          subtitle: "",
        },
        {
          headline: "Heat",
          subtitle: "",
        },
      ],
    };
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
