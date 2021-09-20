<template>
  <div class="custom-select" :tabindex="tabindex" @blur="open = false">
    <div class="selected" :class="{ open: open }" @click="open = !open">
      <img :src="selected.flag" alt="" />
    </div>
    <div class="items" :class="{ selectHide: !open }">
      <div class="item" v-for="(option, i) in options" :key="i" @click="handleSelect(option, i)">
        <span v-if="tabindex === i">&#10003;</span> <img :src="option.flag" alt="" />
        <p>{{ $t(`locales.${option.language}`) }}</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue"

export default defineComponent({
  name: "TextField",
  props: {
    options: {
      type: Array,
      required: true,
    },
    tabindex: {
      type: Number,
      required: false,
      default: 0,
    },
  },
  emits: ["onChange"],
  setup(props, { emit }) {
    const selected = ref(props.options.length > 0 ? props.options[0] : null)
    const open = ref(false)

    const handleSelect = (option: any, index: number) => {
      selected.value = option
      open.value = false
      emit("onChange", [option.language, index])
    }

    return { selected, open, handleSelect }
  },
})
</script>

<style lang="scss" scoped>
.custom-select {
  position: relative;
  width: 100%;
  text-align: left;
  outline: none;
  height: 47px;
  line-height: 47px;
}

.selected {
  background-color: var(--color-neutral);
  border-radius: 6px;
  border: 1px solid #afafaf;
  color: var(--color-white);
  padding: 8px;
  cursor: pointer;
  user-select: none;
  min-width: 55px;
  display: flex;
}

.selected.open {
  border: 1px solid var(--color-grey);
  border-radius: 6px 6px 0px 0px;
}

.selected:after {
  position: absolute;
  content: "";
  top: 22px;
  right: 10px;
  width: 0;
  height: 0;
  border: 4px solid transparent;
  border-color: var(--color-black) transparent transparent transparent;
}

.items {
  color: var(--color-white);
  border-radius: 0px 0px 6px 6px;
  overflow: hidden;
  border-right: 1px solid var(--color-neutral);
  border-left: 1px solid var(--color-neutral);
  border-bottom: 1px solid var(--color-neutral);
  background-color: var(--color-neutral);
  left: 0;
  right: 0;
  margin-top: 3px;
  border-radius: 8px;
}

.item {
  color: var(--color-black);
  padding: 8px;
  cursor: pointer;
  user-select: none;
  border-bottom: 1px solid var(--color-black);
  display: flex;
  opacity: 0.8;

  span {
    font-size: 22px;
    margin-right: 10px;
  }

  img {
    margin-right: 10px;
  }
}

.item:last-child {
  border-bottom: none;
}

.item:hover {
  border: 1px solid var(--color-black);
  opacity: 1;
}

.selectHide {
  display: none;
}
</style>
