<template>
  <div class="custom-select" :tabindex="tabindex" @blur="open = false">
    <div class="selected" :class="{ open: open }" @click="open = !open">
      <img :src="selected.flag" alt="" />
    </div>
    <div class="items" :class="{ selectHide: !open }">
      <div class="item" v-for="(option, i) in options" :key="i" @click="handleChangeLocale(option, i)">
        <span :class="selected.language === option.language ? 'visible' : 'invisible'"
          ><img :src="Checked" alt="checked" class="checked"
        /></span>
        <img :src="option.flag" alt="" />
        <p class="language">{{ $t(`locales.${option.language}`) }}</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { i18n } from "@/i18n"
import { OptionLanguage } from "@/types/OptionLanguage"
import { defineComponent, ref } from "vue"

export default defineComponent({
  name: "LanguageDropdown",
  setup() {
    const { Checked, FlagEn, FlagVi } = icons
    const options: OptionLanguage[] = [
      { flag: FlagEn, language: "en" },
      { flag: FlagVi, language: "vi" },
    ]
    const selected = ref<OptionLanguage | undefined>(options.find((item) => item.language === i18n.global.locale))
    const tabindex = ref(i18n.global.locale === "en" ? 0 : 1)
    const open = ref(false)

    const handleChangeLocale = (option: OptionLanguage, tabIndex: number) => {
      i18n.global.locale = option.language
      open.value = false
      selected.value = option
      tabindex.value = tabIndex
    }

    return { Checked, options, selected, tabindex, open, handleChangeLocale }
  },
})
</script>

<style lang="scss" scoped>
.custom-select {
  position: relative;
  width: 100%;
  text-align: left;
  outline: none;
  height: 47px;
}

.selected {
  background-color: var(--color-neutral);
  border-radius: 6px;
  border: 1px solid #afafaf;
  color: var(--color-white);
  padding: 8px;
  cursor: pointer;
  user-select: none;
  min-width: 55px;
  display: flex;
}

.selected.open {
  border: 1px solid var(--color-grey);
  border-radius: 6px 6px 0px 0px;
}

.selected:after {
  position: absolute;
  content: "";
  top: 22px;
  right: 10px;
  width: 0;
  height: 0;
  border: 4px solid transparent;
  border-color: var(--color-black) transparent transparent transparent;
}

.items {
  color: var(--color-white);
  border-radius: 0px 0px 6px 6px;
  overflow: hidden;
  border-right: 1px solid var(--color-neutral);
  border-left: 1px solid var(--color-neutral);
  border-bottom: 1px solid var(--color-neutral);
  background-color: var(--color-neutral);
  left: 0;
  right: 0;
  margin-top: 3px;
  border-radius: 8px;
  position: absolute;
  width: fit-content;
}

.item {
  color: var(--color-black);
  padding: 4px 8px;
  cursor: pointer;
  user-select: none;
  border-bottom: 1px solid #c4c4c4;
  display: flex;
  gap: 10px;
  align-items: center;

  .language {
    font-size: 12px;
  }

  .visible {
    opacity: 1;
  }

  .invisible {
    opacity: 0;
  }
}

.item:last-child {
  border-bottom: none;
}

.selectHide {
  display: none;
}
</style>
