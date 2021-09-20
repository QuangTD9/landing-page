<template>
  <section class="footer">
    <div class="top-foot">
      <div class="container">
        <div class="container__block">
          <img class="logo" :src="Logo" alt="logo" />
          <ul>
            <li><img :src="TwitterIcon" alt="twitter" /></li>
            <li><img :src="FacebookIcon" alt="facebook" /></li>
            <li><img :src="LinkedInIcon" alt="linkedin" /></li>
          </ul>
        </div>
        <div class="container__block">
          <p class="t-title">Address</p>
          <div class="block-content">
            <img :src="Location" alt="" />
            <div class="block-content__item">
              <p class="t-description">Valletta Buildings, South Street, Valletta - VLT 1103 Malta, Mỹ</p>
              <p class="t-description">20 Phan Dang Luu street, Hai Chau District, Danang city, Vietnam</p>
            </div>
          </div>
          <div class="block-content">
            <img :src="Mobile" alt="" />
            <div class="block-content__item">
              <p class="t-description">(+1) 555-0108-000 or (+236) 555-0108</p>
            </div>
          </div>
        </div>
        <div class="container__block">
          <p class="t-title">Subscribe</p>
          <div class="block-content">
            <div class="block-content__item">
              <p class="t-description">Subscribe to our newsletter and be the first to know about our updates</p>
              <text-field :placeholder="$t('home.header.labels.enterYourEmail')" :icon="ArrowRightWhiteIcon" />
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="bottom-foot"><p>2017 Copyright. Policy.</p></div>
  </section>
</template>

<script lang="ts">
import { icons } from "@/assets/icons"
import { logos } from "@/assets/logos"
import { defineComponent } from "vue"
import TextField from "@/components/shared/TextField.vue"

export default defineComponent({
  name: "Footer",
  components: { TextField },
  setup() {
    const { TwitterIcon, FacebookIcon, LinkedInIcon, Location, Mobile, ArrowRightWhiteIcon } = icons
    const { Logo } = logos

    return { TwitterIcon, FacebookIcon, LinkedInIcon, Location, Mobile, Logo, ArrowRightWhiteIcon }
  },
})
</script>
<style lang="scss" scoped>
.footer {
  color: #ffffff;

  .top-foot {
    background: linear-gradient(180deg, rgba(0, 10, 255, 0.5) 0%, rgba(0, 0, 0, 0) 136.61%),
      linear-gradient(0deg, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0)), url("../../assets/icons/background-footer.svg");
    padding: 8rem 19rem;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: bottom;

    .container {
      display: flex;
      gap: 2rem;

      &__block {
        display: flex;
        flex-direction: column;
        gap: 2rem;
        flex-basis: 33%;

        .logo {
          max-width: 150px;
        }

        ul {
          display: flex;
          gap: 15px;
        }

        .block-content {
          display: flex;
          gap: 13px;
          align-items: flex-start;

          &__item {
            display: flex;
            gap: 10px;
            flex-direction: column;

            &::v-deep input {
              background-color: transparent;
              border: 1px solid #ffffff;
              color: #ffffff;

              &::placeholder {
                color: #ffffff;
              }
            }
          }
        }
      }
    }

    .t-description {
      color: #ffffff;
    }
  }

  .bottom-foot {
    height: 80px;
    background-color: #000000;
    display: flex;
    align-items: center;

    p {
      font-size: 18px;
      line-height: 126%;
      text-align: center;
      width: 100%;
    }
  }
}
</style>
