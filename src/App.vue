<template>
  <view-header></view-header>
  <view-about-us></view-about-us>
  <view-witch-pin></view-witch-pin>
  <view-our-partners></view-our-partners>
  <view-footer></view-footer>
  <view-scroll-back></view-scroll-back>
</template>

<script lang="ts">
import "./assets/styles/global.css"
import "swiper/swiper.scss"
import "swiper/components/navigation/navigation.scss"
import "swiper/components/pagination/pagination.scss"
import SwiperCore, { Navigation, Autoplay } from "swiper"
import { defineComponent } from "vue"
import ViewHeader from "./components/views/Header.vue"
import ViewAboutUs from "./components/views/AboutUs.vue"
import ViewScrollBack from "./components/views/SrcollBack.vue"
import ViewWitchPin from "./components/views/WitchPin.vue"
import ViewOurPartners from "./components/views/OurPartners.vue"
import ViewFooter from "./components/views/Footer.vue"

SwiperCore.use([Navigation, Autoplay])

export default defineComponent({
  name: "App",
  components: {
    ViewHeader,
    ViewAboutUs,
    ViewScrollBack,
    ViewWitchPin,
    ViewOurPartners,
    ViewFooter,
  },
})
</script>
