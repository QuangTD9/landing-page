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
          <p class="pf-bold">{{ displayDays }}</p>
          <span class="t-title">{{ $t("home.header.labels.days") }}</span>
        </div>
        &#58;
        <div class="header-timer-item">
          <p class="pf-bold">{{ displayHours }}</p>
          <span class="t-title">{{ $t("home.header.labels.hours") }}</span>
        </div>
        &#58;
        <div class="header-timer-item">
          <p class="pf-bold">{{ displayMinutes }}</p>
          <span class="t-title">{{ $t("home.header.labels.minutes") }}</span>
        </div>
        &#58;
        <div class="header-timer-item">
          <p class="pf-bold">{{ displaySeconds }}</p>
          <span class="t-title">{{ $t("home.header.labels.second") }}</span>
        </div>
      </div>
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
import { computed, defineComponent, onMounted, ref } from "vue"
import MenuHeader from "@/components/blocks/Header/Menu.vue"
import TextField from "@/components/shared/TextField.vue"
import { logos } from "../assets/logos"
import { images } from "@/assets/images"

export default defineComponent({
  name: "Header",
  components: {
    MenuHeader,
    TextField,
  },
  setup() {
    const { Logo } = logos
    const { Fairy } = images

    const displayDays = ref<string | number>(0)
    const displayHours = ref<string | number>(0)
    const displayMinutes = ref<string | number>(0)
    const displaySeconds = ref<string | number>(0)

    const _seconds = computed(() => 1000)
    const _minutes = computed(() => _seconds.value * 60)
    const _hours = computed(() => _minutes.value * 60)
    const _days = computed(() => _hours.value * 24)

    const showRemaining = () => {
      const timer = setInterval(() => {
        const now = new Date()
        const end = new Date(2022, 0, 1)
        const distance = end.getTime() - now.getTime()

        if (distance < 0) {
          clearInterval(timer)
          return
        }

        const days = Math.floor(distance / _days.value)
        const hours = Math.floor((distance % _days.value) / _hours.value)
        const minutes = Math.floor((distance % _hours.value) / _minutes.value)
        const seconds = Math.floor((distance % _minutes.value) / _seconds.value)

        displayMinutes.value = minutes < 10 ? `0${minutes}` : minutes
        displaySeconds.value = seconds < 10 ? `0${seconds}` : seconds
        displayHours.value = hours < 10 ? `0${hours}` : hours
        displayDays.value = days < 10 ? `0${days}` : days
      }, 1000)
    }

    onMounted(() => {
      showRemaining()
    })

    return { Logo, Fairy, displayDays, displayHours, displayMinutes, displaySeconds }
  },
})
</script>
<style src="./Header.scss" lang="scss" scoped></style>
