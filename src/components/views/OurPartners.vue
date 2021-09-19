<template>
  <section class="our-partners">
    <p class="pf-bold">Our Partners</p>
    <logo-slider></logo-slider>
  </section>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import LogoSlider from "@/components/blocks/ourPartners/LogoSlider.vue"
import { defineComponent } from "vue"

export default defineComponent({
  name: "OurPartners",
  components: { LogoSlider },
  setup() {
    const { CalendarTick, People, Pentool } = icons

    return { CalendarTick, People, Pentool }
  },
})
</script>
<style lang="scss" scoped>
.our-partners {
  padding: 5rem 15rem;
  display: flex;
  flex-direction: column;
  text-align: center;
  gap: 3rem;
  background-color: #f6f6f6;
  margin-top: 130px;
}
</style>
