<template>
  <div class="banner">
    <div class="bg-fairy">
      <!-- <img :src="Fairy" alt="fairy" /> -->
    </div>
    <div class="bg-header">
      <!-- <img :src="BackgroundHeader" alt="backfround header" /> -->
    </div>
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"

export default defineComponent({
  name: "Banner",
  setup() {
    const { BackgroundHeader, Fairy } = icons

    return {
      BackgroundHeader,
      Fairy,
    }
  },
})
</script>

<style lang="scss" scoped>
.banner {
  .bg-header {
    background-image: url("../../../assets/icons/background-header.svg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: bottom;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    position: absolute;
    z-index: -1;
  }

  .bg-fairy {
    background-image: url("../../../assets/icons/fairy.svg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: bottom;
    width: 45%;
    height: 100%;
    position: absolute;
    top: 0;
  }
}
</style>
