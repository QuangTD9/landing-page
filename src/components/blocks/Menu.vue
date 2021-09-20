<template>
  <div>
    <div v-if="!isShowMenu" class="items">
      <ul class="items">
        <li>
          <a href="#about-us" class="t-title">{{ $t("home.header.menu.labels.aboutUs") }}</a>
        </li>
        <li>
          <a href="#our-games" class="t-title">{{ $t("home.header.menu.labels.games") }}</a>
        </li>
        <li>
          <a href="#our-partners" class="t-title">{{ $t("home.header.menu.labels.partners") }}</a>
        </li>
        <li>
          <a href="#footer" class="t-title">{{ $t("home.header.menu.labels.contactUs") }}</a>
        </li>
      </ul>
    </div>

    <img v-else @click="handleOpenNavigation" :src="Menu" alt="menu" />
    <navigation-mobile @onClose="handleClose" v-show="isShowNavigation && isShowMenu"></navigation-mobile>
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent, onMounted, onUnmounted, ref } from "vue"
import NavigationMobile from "@/components/blocks/NavigationMobile.vue"

export default defineComponent({
  name: "Menu",
  components: { NavigationMobile },
  setup() {
    const { Menu } = icons
    const isShowMenu = ref(false)
    const isShowNavigation = ref(false)

    onMounted(() => {
      window.innerWidth < 1024 ? (isShowMenu.value = true) : (isShowMenu.value = false)
      window.addEventListener("resize", handleWindowResize)
    })

    const handleWindowResize = () => (window.innerWidth < 1024 ? (isShowMenu.value = true) : (isShowMenu.value = false))

    const handleOpenNavigation = () => (isShowNavigation.value = true)

    const handleClose = () => (isShowNavigation.value = false)

    onUnmounted(() => {
      window.removeEventListener("resize", handleWindowResize)
    })

    return { Menu, isShowMenu, isShowNavigation, handleOpenNavigation, handleClose }
  },
})
</script>
<style lang="scss" scoped>
.items {
  display: flex;
  gap: 85px;
  z-index: 15;
  .t-title {
    text-transform: uppercase;
    font-size: 14px;
    line-height: 17.5px;
    color: var(--color-white) !important;
  }
}
</style>
