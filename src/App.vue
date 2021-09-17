<template>
  <header-page />
  <about-us-page />
  <scroll-back />
</template>

<script lang="ts">
import { defineComponent } from "vue"
import HeaderPage from "./components/views/Header.vue"
import AboutUsPage from "./components/views/AboutUs.vue"
import ScrollBack from "./components/views/SrcollBack.vue"
import "./assets/styles/global.css"

export default defineComponent({
  name: "App",
  components: {
    HeaderPage,
    ScrollBack,
    AboutUsPage,
  },
})
</script>
