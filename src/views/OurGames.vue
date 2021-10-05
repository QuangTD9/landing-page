<template>
  <section class="our-games">
    <p class="pf-bold">{{ $t(`home.ourGames.labels.ourGames`) }}</p>
    <p class="t-description">
      {{ $t(`home.ourGames.labels.ourGamesDescription`) }}
    </p>
    <div class="container">
      <div v-for="(image, index) in gridImages" :key="index" class="container__item">
        <div class="card-image">
          <img :src="image" />
          <div class="card-text">
            <p class="t-title">{{ $t(`home.ourGames.labels.textTitle${index}`) }}</p>
            <span class="t-description">
              {{ $t(`home.ourGames.labels.textDescription`) }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { images } from "@/assets/images"
import { defineComponent } from "vue"

export default defineComponent({
  name: "OurGames",
  setup() {
    const {
      OurGame1,
      OurGame2,
      OurGame3,
      OurGame4,
      OurGame5,
      OurGame6,
      OurGame7,
      OurGame8,
      OurGame9,
      OurGame10,
      OurGame11,
      OurGame12,
    } = images

    const gridImages = [
      OurGame1,
      OurGame2,
      OurGame3,
      OurGame4,
      OurGame5,
      OurGame6,
      OurGame7,
      OurGame8,
      OurGame9,
      OurGame10,
      OurGame11,
      OurGame12,
    ]

    return { gridImages }
  },
})
</script>
<style lang="scss" scoped>
@import "../assets/styles/mixins.scss";
@import "../assets/styles/variables.scss";

.our-games {
  padding: 0 4rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
  margin-top: 120px;

  .t-description {
    max-width: 830px;
    text-align: center;
  }

  .container {
    display: grid;
    grid-gap: 1.5rem;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, auto);
    grid-auto-flow: column;
    place-items: center;
    align-items: start;
    margin-top: 20px;
    position: relative;

    .card-text {
      position: absolute;
      bottom: 40px;
      padding: 0 32px;

      .t-title {
        font-size: 48px;
        margin-bottom: 15px;
      }

      .t-description {
        align-items: flex-end;
        color: var(--color-white);
        text-align: left;
      }
    }

    &__item:nth-child(n + 4):nth-child(-n + 6),
    &__item:nth-child(n + 10):nth-child(-n + 12) {
      height: calc(100% + 100px);
      display: flex;
      align-items: flex-end;
    }

    &__item {
      position: relative;
      width: fit-content;

      .card-image {
        transform: scale(0.9);
        transition: all var(--speed-card-animation) ease-in-out;
      }
      .card-image::before {
        content: "";
        position: absolute;
        top: 0;
        right: 0;
        bottom: 3px;
        left: 0;
        background: linear-gradient(360deg, rgba(0, 9, 225, 0.5) 6.79%, rgba(0, 0, 0, 0) 61.34%);
        border-radius: 6px;
      }
      .card-image:hover {
        transform: scale(1);
      }

      img {
        width: 100%;
        border-radius: 6px;
        box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
      }
    }
  }

  @include responsive(desktop) {
    padding: 0 $SpacingL;
    .container {
      padding: 0;
      grid-gap: 0.1rem;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(6, auto);

      &__item:nth-child(n + 4):nth-child(-n + 6),
      &__item:nth-child(n + 10):nth-child(-n + 12) {
        height: 100%;
      }
      &__item:nth-child(n + 7):nth-child(-n + 12) {
        height: calc(100% + 30px);
        display: flex;
        align-items: flex-end;
      }

      .card-text {
        padding: $SpacingM;
        bottom: 0;

        .t-title {
          font-size: $FontSizeM;
          margin-bottom: $SpacingS;
        }

        // .t-description {
        //   align-items: flex-end;
        //   color: var(--color-white);
        // }
      }
    }
  }
}
</style>
