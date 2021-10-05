<template>
  <section class="header">
    <div class="menu">
      <img :src="Logo" alt="logo" />
      <menu-header />
    </div>
    <div class="header-container">
      <h1 class="pf-bold header-title">{{ $t("home.header.labels.gettingReady") }}</h1>
      <count-down-timer :endDate="'2022/01/01'" />
      <div class="header-form">
        <p>{{ $t("home.header.labels.notice") }}</p>
        <text-field :placeholder="$t('home.header.labels.enterYourEmail')" />
      </div>
    </div>
    <div class="blur"></div>
    <img class="fairy" :src="Fairy" alt="fairy" />
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import MenuHeader from "@/components/blocks/Header/Menu.vue"
import CountDownTimer from "@/components/blocks/Header/CountDownTimer.vue"
import TextField from "@/components/shared/TextField.vue"
import { logos } from "../assets/logos"
import { images } from "@/assets/images"

export default defineComponent({
  name: "Header",
  components: {
    MenuHeader,
    TextField,
    CountDownTimer,
  },
  setup() {
    const { Logo } = logos
    const { Fairy } = images

    return { Logo, Fairy }
  },
})
</script>
<style src="./Header.scss" lang="scss" scoped></style>
