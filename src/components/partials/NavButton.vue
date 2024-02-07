<template>
  <button class="nav-button" :class="{ 'nav-button__label--active': active, }" @mouseover="hover = true" @mouseleave="hover = false">
    <slot name="icon" :icon-color="iconColor"></slot>
    <span class="nav-button__label" :class="{ 'nav-button__label--active': active }">{{ label }}</span>
    <IconChevron :style="{ display: chevron }" :iconColor="iconColor"/>
  </button>
</template>

<script>
import IconChevron from "@/components/icons/IconChevron.vue";
export default {
  name: "NavButton",
  components: {IconChevron},
  data() {
    return {
      hover: false,
    };
  },
  props: {
    label: {
      type: String,
      default: '',
    },
    chevron: {
      type: String,
      default: 'block'
    },
    active: {
      type: Boolean,
      default: false,
    }
  },
  computed: {
    iconColor() {
      if (this.active || this.hover) {
        return '#FFFFFF'
      }

      return '#9197B3'
    },
  },
}
</script>

<style lang="scss" scoped>
.nav-button {
  display: flex;
  align-items: center;
  width: 100%;
  border: none;
  background: transparent;
  padding: 11px;
  cursor: pointer;
  border-radius: 8px;

  &__label {
    font-family: 'Poppins', sans-serif;
    font-weight: normal;
    line-height: 1.5rem;
    padding-left: 14px;
    color: #9197B3;
  }

  &:hover,
  &__label--active {
    background: #5932EA;
    color: white;
  }
}
</style>