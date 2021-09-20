<template>
  <block-header></block-header>
  <view-about-us></view-about-us>
  <view-witch-pin></view-witch-pin>
  <view-our-games></view-our-games>
  <view-our-partners></view-our-partners>
  <block-footer></block-footer>
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
import BlockHeader from "@/components/blocks/Header.vue"
import ViewAboutUs from "@/components/views/AboutUs.vue"
import BlockScrollBack from "@/components/blocks/SrcollBack.vue"
import ViewWitchPin from "@/components/views/WitchPin.vue"
import ViewOurPartners from "@/components/views/OurPartners.vue"
import ViewOurGames from "@/components/views/OurGames.vue"
import BlockFooter from "@/components/blocks/Footer.vue"

SwiperCore.use([Navigation, Autoplay])

export default defineComponent({
  name: "App",
  components: {
    BlockHeader,
    ViewAboutUs,
    BlockScrollBack,
    ViewWitchPin,
    ViewOurPartners,
    BlockFooter,
    ViewOurGames,
  },
})
</script>
