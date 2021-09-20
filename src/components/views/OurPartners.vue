<template>
  <section class="our-partners">
    <p class="pf-bold">{{ $t("home.ourPartners.labels.ourPartners") }}</p>
    <logo-slider></logo-slider>
  </section>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import LogoSlider from "@/components/blocks/LogoSlider.vue"
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
@import "../../assets/styles/mixins.scss";
@import "../../assets/styles/variables.scss";

.our-partners {
  padding: 5rem 15rem;
  display: flex;
  flex-direction: column;
  text-align: center;
  gap: 3rem;
  background-color: #f6f6f6;
  margin-top: 130px;

  @include responsive(desktop) {
    padding: 2rem 0;
  }
}
</style>
