<template>
  <Header />
  <Home />
</template>

<script lang="ts">
import { defineComponent } from "vue"
import Home from "./pages/Home.vue"
import Header from "./components/blocked/Header.vue"
import "./assets/styles/global.css"

export default defineComponent({
  name: "App",
  components: {
    Home,
    Header,
  },
})
</script>
