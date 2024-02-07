<template>
  <div class="wrapper">
    <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M6 12L10 8L6 4" :stroke="iconColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </div>
</template>

<script>
export default {
  name: "IconChevron",
  props: {
    iconColor: String,
  },
}
</script>

<style scoped>
.wrapper {
  margin-left: auto;
}
</style>