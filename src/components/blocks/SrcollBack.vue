<template>
  <div class="vector" @click="handleClickButtonScroll()">
    <img :src="Vector" :class="!isOnTop ? 'arrow-top' : 'arrow-bottom'" alt="vector" />
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent, onMounted, onUnmounted, ref } from "vue"

const SCROLL_HEIGHT = 500

export default defineComponent({
  name: "ScrollBack",
  setup() {
    const { Vector } = icons
    const isOnTop = ref(true)

    onMounted(() => {
      if (window.scrollY > SCROLL_HEIGHT) {
        isOnTop.value = false
      }
      window.addEventListener("scroll", handleScroll)
    })

    const handleScroll = () => {
      if (window.scrollY > SCROLL_HEIGHT) {
        isOnTop.value = false
      } else {
        isOnTop.value = true
      }
    }

    const handleClickButtonScroll = () => {
      isOnTop.value
        ? document.body.scrollIntoView({ behavior: "smooth", block: "end" })
        : document.body.scrollIntoView({ behavior: "smooth", block: "start" })
    }

    onUnmounted(() => {
      window.removeEventListener("scroll", handleScroll)
    })

    return { Vector, isOnTop, handleClickButtonScroll }
  },
})
</script>

<style lang="scss" scoped>
@keyframes arrowTop {
  from {
    transform: rotate(180deg);
  }

  to {
    transform: rotate(180deg);
  }
}

.vector {
  position: fixed;
  background-color: var(--color-white);
  width: 66px;
  height: 66px;
  text-align: center;
  align-content: center;
  border-radius: 50%;
  right: 5rem;
  bottom: 3rem;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
  cursor: pointer;
  display: flex;
  justify-content: center;
  z-index: 10;

  img {
    width: 40%;
  }

  .arrow-bottom {
    transition: var(--speed-card-animation);
    transform: rotate(0);
  }
  .arrow-top {
    transition: var(--speed-card-animation);
    transform: rotate(180deg);
  }
}
</style>
