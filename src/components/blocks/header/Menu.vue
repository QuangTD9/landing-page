<template>
  <div class="items">
    <div>
      <a href="#" class="t-title">{{ $t("home.header.menu.labels.aboutUs") }}</a>
    </div>
    <div>
      <a href="#" class="t-title">{{ $t("home.header.menu.labels.games") }}</a>
    </div>
    <div>
      <a href="#" class="t-title">{{ $t("home.header.menu.labels.partners") }}</a>
    </div>
    <div>
      <a href="#" class="t-title">{{ $t("home.header.menu.labels.contactUs") }}</a>
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
.items {
  display: flex;
  gap: 85px;
  .t-title {
    text-transform: uppercase;
    font-size: 14px;
    line-height: 17.5px;
  }
}
</style>
