<template>
  <view-header></view-header>
  <view-about-us id="about-us"></view-about-us>
  <view-witch-pin></view-witch-pin>
  <view-our-games id="our-games"></view-our-games>
  <view-our-partners id="our-partners"></view-our-partners>
  <view-footer id="footer"></view-footer>
  <block-scroll-back></block-scroll-back>
</template>

<script lang="ts">
// styles
import "@/assets/styles/global.scss"
import "swiper/swiper.scss"
import "swiper/components/navigation/navigation.scss"
import "swiper/components/pagination/pagination.scss"
// components
import SwiperCore, { Navigation, Autoplay } from "swiper"
import { defineComponent } from "vue"
import ViewHeader from "@/views/Header.vue"
import ViewAboutUs from "@/views/AboutUs.vue"
import BlockScrollBack from "@/components/blocks/SrcollBack.vue"
import ViewWitchPin from "@/views/WitchPin.vue"
import ViewOurPartners from "@/views/OurPartners.vue"
import ViewOurGames from "@/views/OurGames.vue"
import ViewFooter from "@/views/Footer.vue"

SwiperCore.use([Navigation, Autoplay])

export default defineComponent({
  name: "App",
  components: {
    ViewHeader,
    ViewAboutUs,
    BlockScrollBack,
    ViewWitchPin,
    ViewOurPartners,
    ViewFooter,
    ViewOurGames,
  },
})
</script>
