<template>
  <section class="about-us">
    <div class="block">
      <p class="pf-bold">{{ $t("home.aboutUs.labels.aboutUs") }}</p>
      <span class="t-description">{{ $t("home.aboutUs.labels.aboutUsDescription") }}</span>
      <div class="block-count">
        <div class="block-count-item">
          <p class="t-title t-blue">600<span>M</span>&#43;</p>
          <p class="t-title">{{ $t("home.aboutUs.labels.users") }}</p>
        </div>
        <div class="block-count-item">
          <p class="t-title t-blue">135&#43;</p>
          <p class="t-title">{{ $t("home.aboutUs.labels.games") }}</p>
        </div>
      </div>
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
  setup() {
    const { CalendarTick, People, Pentool } = icons

    return { CalendarTick, People, Pentool }
  },
})
</script>
<style lang="scss" scoped>
@import "../../assets/styles/mixins.scss";
@import "../../assets/styles/variables.scss";

.about-us {
  display: flex;
  gap: 10px;
  justify-content: center;
  margin-top: 50px;
  padding: 0 $SpacingXL;

  .block {
    max-width: 560px;

    .pf-bold {
      margin-bottom: 20px;
    }

    .t-title {
      color: var(--color-black);
    }

    .t-blue {
      margin-top: 70px;
      color: var(--color-blue);
      font-size: 80px;

      span {
        font-size: 50px;
      }
    }
  }

  .block-right {
    background-color: var(--color-neutral);
    border: 1px solid var(--color-neutral);
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

  @include responsive(desktop) {
    flex-direction: column;
    padding: $SpacingL;
    .block {
      padding: 0 $SpacingL;
      max-width: none;

      .block-count {
        display: flex;
        justify-content: space-around;
        margin: $FontSizeM 0;
      }
      .t-blue {
        font-size: 44px;
        margin-top: 0;
        span {
          font-size: $SpacingLX;
        }
      }
    }
    .block-right {
      padding: $SpacingXL $SpacingM;
    }
  }
}
</style>
