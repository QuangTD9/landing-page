<template>
  <Banner />
  <div class="header">
    <img :src="Logo" alt="logo" />
    <Menu />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import Menu from "../views/header/Menu.vue"
import Banner from "../views/header/Banner.vue"
import { icons } from "../../assets/icons"

export default defineComponent({
  name: "Header",
  components: {
    Menu,
    Banner,
  },
  setup() {
    const { Logo } = icons

    return { Logo }
  },
})
</script>
<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  position: relative;
  align-items: center;
}
</style>
