<template>
  <div class="header-container">
    <div class="header-shadow" />
    <div class="header-content">
      <h1 class="pf-bold header-content-title">{{ $t("home.header.labels.gettingReady") }}</h1>
      <div class="header-content-timer">
        <div class="header-content-timer-item">
          <p class="pf-bold">30</p>
          <span class="t-title">{{ $t("home.header.labels.days") }}</span>
        </div>
        &#58;
        <div class="header-content-timer-item">
          <p class="pf-bold">18</p>
          <span class="t-title">{{ $t("home.header.labels.hours") }}</span>
        </div>
        &#58;
        <div class="header-content-timer-item">
          <p class="pf-bold">20</p>
          <span class="t-title">{{ $t("home.header.labels.minutes") }}</span>
        </div>
        &#58;
        <div class="header-content-timer-item">
          <p class="pf-bold">11</p>
          <span class="t-title">{{ $t("home.header.labels.second") }}</span>
        </div>
      </div>
    </div>
    <div class="header-content t-form">
      <p>{{ $t("home.header.labels.notice") }}</p>
      <text-field :placeholder="$t('home.header.labels.enterYourEmail')" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import TextField from "../../shared/TextField.vue"

export default defineComponent({
  name: "FormHeader",
  components: {
    TextField,
  },
})
</script>

<style src="./FormHeader.scss" lang="scss" scoped></style>
