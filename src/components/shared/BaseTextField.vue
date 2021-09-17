<template>
  <div class="text-outlined">
    <input type="text" :placeholder="placeholder" />
    <img class="arrow-icon" :src="ArrowRightIcon" alt="" />
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"

export default defineComponent({
  name: "BaseTextField",
  props: {
    placeholder: {
      type: String,
    },
  },
  setup() {
    const { ArrowRightIcon } = icons
    return { ArrowRightIcon }
  },
})
</script>

<style lang="scss" scoped>
.text-outlined {
  display: flex;
  position: relative;

  input {
    height: 40px;
    border-radius: 8px;
    padding: 0 14px;
    width: 100%;
    border: none;

    &:focus-visible {
      outline: none;
    }
  }
  .arrow-icon {
    height: 19px;
    width: 19px;
    position: absolute;
    right: 0;
    margin: 12px;
    cursor: pointer;
  }
}
</style>
