<template>
  <div>
    <swiper
      :speed="1000"
      :loop="true"
      :autoplay="{
        delay: 5000,
        pauseOnMouseEnter: true,
      }"
      :space-between="0"
      :navigation="true"
      :breakpoints="{
        380: {
          slidesPerView: 1,
          spaceBetween: 20,
        },
        768: {
          slidesPerView: 3,
          spaceBetween: 20,
        },
        1580: {
          slidesPerView: 5,
          spaceBetween: 20,
        },
      }"
    >
      <swiper-slide v-for="(slide, index) in sliders" :key="index" :virtualIndex="index"
        ><img :src="slide"
      /></swiper-slide>
    </swiper>
  </div>
</template>

<script lang="ts">
import { logos } from "@/assets/logos"
import { defineComponent } from "vue"
import { Swiper, SwiperSlide } from "swiper/vue"

export default defineComponent({
  name: "LogoSlider",
  components: { Swiper, SwiperSlide },
  setup() {
    const { TwoK, BookPro, EAGames, FirstPowerUp, Game, Sega, WaltDisney } = logos

    const sliders = [TwoK, BookPro, EAGames, FirstPowerUp, Game, Sega, WaltDisney]

    return { sliders }
  },
})
</script>
<style lang="scss">
.swiper-button-next {
  background-image: url("../../../assets/icons/arrow-square-right.svg");
  background-repeat: no-repeat;
  background-size: 100% auto;
  background-position: center;
  height: 30px;
  width: 30px;
  z-index: 9999;
  position: absolute;
  right: 20px;
  top: 50%;
}

.swiper-button-prev {
  background-image: url("../../../assets/icons/arrow-square-left.svg");
  background-repeat: no-repeat;
  background-size: 100% auto;
  background-position: center;
  height: 30px;
  width: 30px;
  z-index: 9999;
  position: absolute;
  top: 50%;
  left: 20px;
}

.swiper-button-disabled {
  display: none;
}

.swiper-button-prev::after,
.swiper-button-next::after {
  display: none;
}
</style>
