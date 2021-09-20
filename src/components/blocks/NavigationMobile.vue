<template>
  <div class="navigation">
    <div class="navigation-top">
      <!-- <select v-model="selected">
        <option v-for="item in languages" :key="item.flag" :value="item.value" :style="{ backgroundImage: FlagVi }">
          {{ item.title }}
        </option>
      </select> -->
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
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent, PropType, ref } from "vue"

export default defineComponent({
  name: "NavigationMobile",
  emits: {
    onClose: null,
  },
  setup() {
    const { Close, FlagVi, FlagEn } = icons
    const languages = ref([
      { flag: "us", language: "en", title: "English" },
      { flag: "es", language: "vi", title: "Vietnamese" },
    ])

    return { Close, languages, FlagVi, FlagEn }
  },
})
</script>
<style lang="scss" scoped>
@import "../../assets/styles/variables.scss";

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
