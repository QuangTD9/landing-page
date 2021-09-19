<template>
  <div class="text-outlined">
    <input type="text" :placeholder="placeholder" />
    <img class="arrow-icon" :src="icon" alt="icon" />
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"

export default defineComponent({
  name: "TextField",
  props: {
    placeholder: {
      type: String,
    },
    icon: {
      default: icons.ArrowRightBlackIcon,
    },
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
    border: 1px solid #ffffff;

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
