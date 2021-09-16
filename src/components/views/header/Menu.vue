<template>
  <div class="menu">
    <div>
      <a href="#" class="text-link">{{ $t("home.menu.labels.aboutUs") }}</a>
    </div>
    <div>
      <a href="#" class="text-link">{{ $t("home.menu.labels.games") }}</a>
    </div>
    <div>
      <a href="#" class="text-link">{{ $t("home.menu.labels.partners") }}</a>
    </div>
    <div>
      <a href="#" class="text-link">{{ $t("home.menu.labels.contactUs") }}</a>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"

export default defineComponent({
  name: "Menu",
})
</script>
<style lang="scss" scoped>
.menu {
  display: flex;
  gap: 85px;
  .text-link {
    font-family: "Montserrat Bold";
    font-weight: 700;
    color: #ffffff;
    text-transform: uppercase;
    font-size: 14px;
    line-height: 17.5px;
  }
}
</style>
