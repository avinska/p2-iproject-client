<script>
import { mapActions } from "pinia";
import { useAllStore } from "../stores/all";

export default {
  name: "CategoryBar",
  data() {
    return {
      categories: [
        "All",
        "Live",
        "Sewing",
        "Mixes",
        "Baking",
        "Yoga",
        "Work out",
        "React routers",
        "Marine biology",
        "Cooking shows",
        "Gaming",
        "Culinary arts",
        "Christmas music",
        "Piano",
        "Anime",
      ],
    };
  },
  methods: {
    ...mapActions(useAllStore, ["fetchVideos"]),
    handleClick(category) {
      this.fetchVideos(category);
    },
  },
};
</script>

<template>
  <div class="d-flex container-fluid justify-content-center py-2 w-100 no-wrap">
    <button
      v-for="(cat, i) in categories"
      :key="'cat' + i"
      class="btn btn-light mx-1 text-decoration-none size-12"
      @click="handleClick(cat)"
    >
      {{ cat }}
    </button>
  </div>
</template>

<style scoped>
.size-12 {
  font-size: 14px;
}

.rounder {
}
</style>
