<template>
  <section class="pin">
    <img class="pin-witch" :src="Wich" alt="" />
    <img class="pin-map" :src="PinMap" alt="" />
  </section>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"

export default defineComponent({
  name: "Pin",
  setup() {
    const { Wich, PinMap } = icons

    return { Wich, PinMap }
  },
})
</script>
<style lang="scss" scoped>
@keyframes example {
  0%,
  100% {
    top: 0;
  }
  50% {
    top: 16%;
  }
}
.pin {
  margin-top: 10rem;
  align-items: center;
  position: relative;
  height: 57vw;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0) 60.6%, #ffffff 82.58%);

  &-witch {
    width: 30%;
    right: 36%;
    animation: example 5s infinite;
    position: absolute;
  }

  &-map {
    width: 100%;
    position: absolute;
    bottom: 0;
    z-index: -1;
  }
}
</style>
