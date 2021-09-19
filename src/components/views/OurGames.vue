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
  name: "OurGames",
  setup() {
    const { Wich, PinMap } = icons

    return { Wich, PinMap }
  },
})
</script>
<style lang="scss" scoped>
.pin {
  margin-top: 68px;
  display: flex;
  flex-direction: column;
  align-items: center;

  &-witch {
    margin-bottom: -100px;
  }

  &-map {
    z-index: -1;
  }
}
</style>
