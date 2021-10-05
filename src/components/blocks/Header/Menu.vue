<template>
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
      <li>
        <language-dropdown class="select" />
      </li>
    </ul>
  </div>

  <img v-else @click="handleOpenNavigation" :src="Menu" alt="menu" />
  <navigation-mobile v-if="isShowNavigation && isShowMenu" @onClose="handleClose"></navigation-mobile>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent, onMounted, onUnmounted, ref } from "vue"
import NavigationMobile from "@/components/blocks/Header/NavigationMobile.vue"
import LanguageDropdown from "@/components/blocks/Header/LanguageDropdown.vue"

export default defineComponent({
  name: "Menu",
  components: { NavigationMobile, LanguageDropdown },
  setup() {
    const { Menu } = icons

    const isShowMenu = ref(false)
    const isShowNavigation = ref(false)

    onMounted(() => {
      window.innerWidth < 1024 ? (isShowMenu.value = true) : (isShowMenu.value = false)
      window.addEventListener("resize", handleWindowResize)
    })

    const handleWindowResize = () => (window.innerWidth < 1024 ? (isShowMenu.value = true) : (isShowMenu.value = false))

    const handleOpenNavigation = () => {
      document.body.style.overflowY = "hidden"
      isShowNavigation.value = true
    }

    const handleClose = () => {
      isShowNavigation.value = false
      document.body.style.overflowY = "auto"
    }

    onUnmounted(() => {
      window.removeEventListener("resize", handleWindowResize)
    })

    return {
      Menu,
      isShowMenu,
      isShowNavigation,
      handleOpenNavigation,
      handleClose,
    }
  },
})
</script>
<style lang="scss" scoped>
.items {
  display: flex;
  gap: 85px;
  z-index: 15;
  align-items: center;

  .t-title {
    text-transform: uppercase;
    font-size: 14px;
    line-height: 17.5px;
    color: var(--color-white) !important;
  }

  .select {
    background-color: transparent;
    border: none;

    :deep .selected {
      background-color: transparent;
      border: none;

      &::after {
        border-color: var(--color-white) transparent transparent transparent;
      }
    }

    :deep .items {
      border-right: 1px solid var(--color-white);
      border-left: 1px solid var(--color-white);
      border-bottom: 1px solid var(--color-white);
      background-color: var(--color-white);
      margin-left: -105px;
    }
  }
}
</style>
