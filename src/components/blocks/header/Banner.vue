<template>
  <div class="banner">
    <div class="banner-fairy"></div>
    <div class="banner-background"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"

export default defineComponent({
  name: "Banner",
})
</script>

<style lang="scss" scoped>
.banner {
  &-background {
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

  &-fairy {
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
