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
import ViewHeader from "@/components/views/Header.vue"
import ViewAboutUs from "@/components/views/AboutUs.vue"
import BlockScrollBack from "@/components/blocks/SrcollBack.vue"
import ViewWitchPin from "@/components/views/WitchPin.vue"
import ViewOurPartners from "@/components/views/OurPartners.vue"
import ViewOurGames from "@/components/views/OurGames.vue"
import ViewFooter from "@/components/views/Footer.vue"

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
