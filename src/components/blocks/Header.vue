<template>
  <section class="header">
    <div class="menu">
      <img :src="Logo" alt="logo" />
      <menu-header />
    </div>
    <div class="header-container">
      <h1 class="pf-bold header-title">{{ $t("home.header.labels.gettingReady") }}</h1>
      <div class="header-timer">
        <div class="header-timer-item">
          <p class="pf-bold">30</p>
          <span class="t-title">{{ $t("home.header.labels.days") }}</span>
        </div>
        &#58;
        <div class="header-timer-item">
          <p class="pf-bold">18</p>
          <span class="t-title">{{ $t("home.header.labels.hours") }}</span>
        </div>
        &#58;
        <div class="header-timer-item">
          <p class="pf-bold">20</p>
          <span class="t-title">{{ $t("home.header.labels.minutes") }}</span>
        </div>
        &#58;
        <div class="header-timer-item">
          <p class="pf-bold">11</p>
          <span class="t-title">{{ $t("home.header.labels.second") }}</span>
        </div>
      </div>
      <div class="header-form">
        <p>{{ $t("home.header.labels.notice") }}</p>
        <text-field :placeholder="$t('home.header.labels.enterYourEmail')" />
      </div>
    </div>
    <img class="fairy" :src="Fairy" alt="fairy" />
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import MenuHeader from "@/components/blocks/Menu.vue"
import TextField from "@/components/shared/TextField.vue"
import { logos } from "../../assets/logos"
import { icons } from "@/assets/icons"

export default defineComponent({
  name: "Header",
  components: {
    MenuHeader,
    TextField,
  },
  setup() {
    const { Logo } = logos
    const { Fairy } = icons

    return { Logo, Fairy }
  },
})
</script>
<style src="./Header.scss" lang="scss" scoped></style>
