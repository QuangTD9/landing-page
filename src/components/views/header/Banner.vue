<template>
  <div class="banner">
    <div class="bg-image" />
    <div class="bg-fairy" />
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
  width: 100%;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
}
.bg-image {
  background-image: url("../../../assets/icons/background-header.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: bottom;
  width: 100%;
  height: 100%;
  position: absolute;
}
.bg-fairy {
  background-image: url("../../../assets/icons/fairy.svg");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: bottom;
  width: 45%;
  height: 100%;
  position: absolute;
}
</style>
