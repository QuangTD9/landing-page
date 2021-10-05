<template>
  <section class="pin">
    <img class="pin-witch" :src="Witch" alt="" />
    <img class="pin-map" :src="PinMap" alt="" />
  </section>
</template>

<script lang="ts">
import { images } from "@/assets/images"
import { defineComponent } from "vue"

export default defineComponent({
  name: "Pin",
  setup() {
    const { Witch, PinMap } = images

    return { Witch, PinMap }
  },
})
</script>
<style lang="scss" scoped>
@import "../assets/styles/mixins.scss";
@import "../assets/styles/variables.scss";

@keyframes animation {
  0%,
  100% {
    top: 0;
  }
  50% {
    top: 16%;
  }
}
.pin {
  margin-top: 3rem;
  align-items: center;
  position: relative;
  height: 57vw;
  background: linear-gradient(180deg, rgba(255, 255, 255, 0) 60.6%, var(--color-white) 82.58%);

  &-witch {
    width: 35%;
    right: 36%;
    animation: animation var(--speed-switch-animation) infinite;
    position: absolute;
  }

  &-map {
    width: 100%;
    position: absolute;
    bottom: 0;
    z-index: -1;
  }

  @include responsive(tablet) {
    height: 67vw;
    &-witch {
      width: 45%;
      right: 28%;
    }
  }
}
</style>
