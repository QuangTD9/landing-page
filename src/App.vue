<template>
  <header-page />
  <home />
  <scroll-back />
</template>

<script lang="ts">
import { defineComponent } from "vue"
import Home from "./pages/Home.vue"
import HeaderPage from "./components/blocked/Header.vue"
import ScrollBack from "./components/blocked/SrcollBack.vue"
import "./assets/styles/global.css"

export default defineComponent({
  name: "App",
  components: {
    Home,
    HeaderPage,
    ScrollBack,
  },
})
</script>
