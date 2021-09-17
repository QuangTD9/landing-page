<template>
  <div class="vector">
    <img :src="Vector" alt="vector" />
  </div>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { defineComponent } from "vue"

export default defineComponent({
  name: "ScrollBack",
  setup() {
    const { Vector } = icons

    return { Vector }
  },
})
</script>

<style lang="scss" scoped>
.vector {
  position: fixed;
  background-color: #ffffff;
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
}
</style>
