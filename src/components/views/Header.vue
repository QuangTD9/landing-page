<template>
  <section class="header">
    <div class="menu">
      <img :src="Logo" alt="logo" />
      <menu-header />
    </div>
    <banner />
    <form-header />
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue"
import MenuHeader from "../blocked/header/Menu.vue"
import Banner from "../blocked/header/Banner.vue"
import FormHeader from "../blocked/header/FormHeader.vue"
import { icons } from "../../assets/icons"

export default defineComponent({
  name: "Header",
  components: {
    MenuHeader,
    Banner,
    FormHeader,
  },
  setup() {
    const { Logo } = icons

    return { Logo }
  },
})
</script>
<style lang="scss" scoped>
.header {
  min-height: 550px;
  height: 100vh;
}
.menu {
  display: flex;
  justify-content: space-between;
  position: inherit;
  align-items: center;
  padding: 1rem 4rem;
}
</style>
