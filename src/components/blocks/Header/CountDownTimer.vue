<template>
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
</template>

<script lang="ts">
import { computed, defineComponent, onMounted, ref } from "vue"

export default defineComponent({
  name: "CountDownTimer",
  props: {
    endDate: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const displayDays = ref<string | number>(0)
    const displayHours = ref<string | number>(0)
    const displayMinutes = ref<string | number>(0)
    const displaySeconds = ref<string | number>(0)

    const _seconds = computed(() => 1000)
    const _minutes = computed(() => _seconds.value * 60)
    const _hours = computed(() => _minutes.value * 60)
    const _days = computed(() => _hours.value * 24)

    const formatTimer = (time: string | number): string | number => (time < 10 ? `0${time}` : time)

    const showRemaining = () => {
      const timer = setInterval(() => {
        const now = new Date()
        const end = new Date(props.endDate)
        const distance = end.getTime() - now.getTime()

        if (distance < 0) {
          clearInterval(timer)
          return
        }

        const days = Math.floor(distance / _days.value)
        const hours = Math.floor((distance % _days.value) / _hours.value)
        const minutes = Math.floor((distance % _hours.value) / _minutes.value)
        const seconds = Math.floor((distance % _minutes.value) / _seconds.value)

        displayMinutes.value = formatTimer(minutes)
        displaySeconds.value = formatTimer(seconds)
        displayHours.value = formatTimer(hours)
        displayDays.value = formatTimer(days)
      }, 1000)
    }

    onMounted(() => {
      showRemaining()
    })

    return { displayDays, displayHours, displayMinutes, displaySeconds }
  },
})
</script>

<style lang="scss" scoped>
@import "../../../assets/styles/variables.scss";
.header-timer {
  display: flex;
  gap: 4rem;
  color: var(--color-black);
  background-color: var(--color-white);
  border-radius: 21px;
  padding: 20px 40px;
  text-align: center;
  align-items: center;
  font-size: $FontSizeXL;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
  margin-bottom: 80px;
  z-index: 3;

  &-item {
    display: flex;
    flex-direction: column;

    .t-title {
      color: var(--color-black);
      font-size: $FontSizeS;
      margin-top: $SpacingXS;
    }
  }
}
</style>
