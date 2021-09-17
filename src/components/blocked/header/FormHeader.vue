<template>
  <div class="header-container">
    <div class="header-shadow" />
    <div class="header-content">
      <h1 class="pf-bold header-content-title">{{ $t("home.header.labels.gettingReady") }}</h1>
      <div class="header-content-timer">
        <div class="header-content-timer-item">
          <p class="pf-bold">30</p>
          <span>{{ $t("home.header.labels.days") }}</span>
        </div>
        &#58;
        <div class="header-content-timer-item">
          <p class="pf-bold">18</p>
          <span>{{ $t("home.header.labels.hours") }}</span>
        </div>
        &#58;
        <div class="header-content-timer-item">
          <p class="pf-bold">20</p>
          <span>{{ $t("home.header.labels.minutes") }}</span>
        </div>
        &#58;
        <div class="header-content-timer-item">
          <p class="pf-bold">11</p>
          <span>{{ $t("home.header.labels.second") }}</span>
        </div>
      </div>
    </div>
    <div class="header-content t-form">
      <p>{{ $t("home.header.labels.notice") }}</p>
      <base-text-field :placeholder="$t('home.header.labels.enterYourEmail')" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import BaseTextField from "../../shared/BaseTextField.vue"

export default defineComponent({
  name: "FormHeader",
  components: {
    BaseTextField,
  },
})
</script>

<style lang="scss" scoped>
.header-container {
  display: flex;
  flex-direction: column;
  color: #ffffff;
  align-items: center;
  gap: 90px;
  margin-top: 120px;

  .header-shadow {
    position: absolute;
    background: radial-gradient(
      39.72% 32.79% at 50.81% 68.15%,
      #210544 0%,
      rgba(23, 5, 68, 0.71) 50.52%,
      rgba(23, 5, 68, 0) 100%
    );
    backdrop-filter: blur(3px);
    width: 54%;
    height: 50%;
    top: 30%;
    border-radius: 30%;
  }

  .header-content {
    display: flex;
    flex-direction: column;
    gap: 21px;
    z-index: 1;
    &-title {
      font-size: 80px;
      letter-spacing: 0.6px;
    }

    &-timer {
      display: flex;
      gap: 4rem;
      color: #000000;
      background-color: #ffffff;
      border-radius: 21px;
      padding: 20px 40px;
      text-align: center;
      align-items: center;
      font-size: 60px;
      box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);

      &-item {
        display: flex;
        flex-direction: column;
        span {
          font-family: "Montserrat Bold";
          font-size: 16px;
          margin-top: 18px;
        }
      }
    }
  }

  .t-form {
    max-width: 488px;
    text-align: center;
  }
}
</style>
