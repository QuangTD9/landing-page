<template>
  <section class="about-us">
    <div class="block">
      <p class="pf-bold">{{ $t("home.aboutUs.labels.aboutUs") }}</p>
      <span class="t-description">{{ $t("home.aboutUs.labels.aboutUsDescription") }}</span>
      <p class="t-blue">600<span>M</span>&#43;</p>
      <p class="t-title">{{ $t("home.aboutUs.labels.users") }}</p>
      <p class="t-blue">135&#43;</p>
      <p class="t-title">{{ $t("home.aboutUs.labels.games") }}</p>
    </div>
    <div class="block block-right">
      <div class="block-right-item">
        <img :src="CalendarTick" alt="" />
        <div class="block-right-item-content">
          <p class="t-title">{{ $t("home.aboutUs.labels.hour") }}</p>
          <span class="t-description">{{ $t("home.aboutUs.labels.hourDescription") }}</span>
        </div>
      </div>
      <div class="block-right-item">
        <img :src="Pentool" alt="" />
        <div class="block-right-item-content">
          <p class="t-title">{{ $t("home.aboutUs.labels.design") }}</p>
          <span class="t-description">{{ $t("home.aboutUs.labels.designDescription") }}</span>
        </div>
      </div>
      <div class="block-right-item">
        <img :src="People" alt="" />
        <div class="block-right-item-content">
          <p class="t-title">{{ $t("home.aboutUs.labels.team") }}</p>
          <span class="t-description">{{ $t("home.aboutUs.labels.teamDescription") }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"

export default defineComponent({
  name: "AboutUs",
  components: {},
  setup() {
    const { CalendarTick, People, Pentool } = icons

    return { CalendarTick, People, Pentool }
  },
})
</script>
<style lang="scss" scoped>
.about-us {
  display: flex;
  gap: 10px;
  justify-content: center;
  margin-top: 50px;

  .block {
    max-width: 560px;
    font-family: "Montserrat Bold";

    .pf-bold {
      margin-bottom: 20px;
    }

    .t-blue {
      margin-top: 70px;
      color: #079bee;
      font-size: 80px;

      span {
        font-size: 50px;
      }
    }
    .t-title {
      font-size: 24px;
    }
  }

  .block-right {
    background-color: #eeeeee;
    border: 1px solid #eeeeee;
    display: flex;
    flex-direction: column;
    gap: 41px;
    padding: 0 58px;
    justify-content: center;
    box-sizing: border-box;

    &-item {
      display: flex;
      gap: 24px;
      align-items: flex-start;

      &-content {
        display: flex;
        flex-direction: column;
        gap: 10px;
      }
    }
  }
}
</style>
