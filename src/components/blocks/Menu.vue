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
        <li>
          <custom-select
            :tabindex="tabIndex"
            :options="languages"
            :default="'go'"
            class="select"
            @onChange="handleChangeLocale($event)"
          />
        </li>
      </ul>
    </div>

    <img v-else @click="handleOpenNavigation" :src="Menu" alt="menu" />
    <navigation-mobile
      :tabindex="tabIndex"
      :languages="languages"
      @onClose="handleClose"
      @onChangeLanguage="handleChangeLocale($event)"
      v-show="isShowNavigation && isShowMenu"
    ></navigation-mobile>
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent, onMounted, onUnmounted, ref } from "vue"
import NavigationMobile from "@/components/blocks/NavigationMobile.vue"
import CustomSelect from "@/components/shared/Select.vue"
import { i18n } from "@/i18n"

export default defineComponent({
  name: "Menu",
  components: { NavigationMobile, CustomSelect },
  setup() {
    const { Menu, FlagEn, FlagVi } = icons

    const isShowMenu = ref(false)
    const isShowNavigation = ref(false)
    const tabIndex = ref(0)

    const languages = ref([
      { flag: FlagEn, language: "en", title: "English" },
      { flag: FlagVi, language: "vi", title: "Vietnamese" },
    ])

    onMounted(() => {
      window.innerWidth < 1024 ? (isShowMenu.value = true) : (isShowMenu.value = false)
      window.addEventListener("resize", handleWindowResize)
    })

    const handleWindowResize = () => (window.innerWidth < 1024 ? (isShowMenu.value = true) : (isShowMenu.value = false))

    const handleOpenNavigation = () => (isShowNavigation.value = true)

    const handleClose = () => (isShowNavigation.value = false)

    const handleChangeLocale = (value: any[]) => {
      i18n.global.locale = value[0]
      tabIndex.value = value[1]
    }

    onUnmounted(() => {
      window.removeEventListener("resize", handleWindowResize)
    })

    return {
      Menu,
      isShowMenu,
      tabIndex,
      isShowNavigation,
      handleOpenNavigation,
      handleClose,
      languages,
      handleChangeLocale,
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
    }
  }
}
</style>
