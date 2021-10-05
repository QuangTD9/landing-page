<template>
  <transition name="nav-mobile">
    <div class="navigation">
      <div class="navigation-top">
        <div>
          <language-dropdown class="select" />
        </div>
        <img @click="$emit('onClose')" :src="Close" alt="close" />
      </div>
      <ul class="navigation-bottom">
        <li>
          <a @click="$emit('onClose')" href="#about-us">{{ $t("home.header.menu.labels.aboutUs") }}</a>
        </li>
        <li>
          <a @click="$emit('onClose')" href="#our-games">{{ $t("home.header.menu.labels.games") }}</a>
        </li>
        <li>
          <a @click="$emit('onClose')" href="#our-partners">{{ $t("home.header.menu.labels.partners") }}</a>
        </li>
        <li>
          <a @click="$emit('onClose')" href="#footer">{{ $t("home.header.menu.labels.contactUs") }}</a>
        </li>
      </ul>
    </div>
  </transition>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"
import LanguageDropdown from "@/components/blocks/LanguageDropdown.vue"

export default defineComponent({
  name: "NavigationMobile",
  emits: ["onClose"],
  components: { LanguageDropdown },
  setup() {
    const { Close } = icons

    return { Close }
  },
})
</script>
<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";
.nav-mobile-enter-active,
.nav-mobile-leave-active {
  transition: 0.7s ease all;
}

.nav-mobile-enter-from,
.nav-mobile-leave-to {
  transform: translateY(-100%);
}

.nav-mobile-enter-to {
  transform: translateY(0);
}

.navigation {
  position: fixed;
  top: 0;
  width: 100%;
  height: 100%;
  left: 0;
  background-color: var(--color-white);
  z-index: 11;
  padding: $SpacingXL $SpacingM;
  font-family: var(--font-mentserrat-bold);
  font-size: 14px;
  box-sizing: border-box;
  overflow: auto;

  ul {
    margin-top: $SpacingL;
    li {
      border-bottom: 1px solid var(--color-neutral);
      padding: 2rem;
      text-align: center;
    }
    li:last-child {
      border-bottom: none;
    }
  }
  a {
    color: var(--color-black);
    text-transform: uppercase;
  }

  .navigation-top {
    display: flex;
    justify-content: space-between;
  }
  img {
    cursor: pointer;
  }
}
</style>
