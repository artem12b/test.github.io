<template>
  <div class="logo">
    <IconLogo/>
    <span class="logo__label">Dashboard</span>
  </div>
</template>

<script>
import IconLogo from "@/components/icons/IconLogo.vue";
export default {
  name: "LogoComponent",
  components: {IconLogo}
}
</script>

<style scoped>
.logo {
  display: flex;
  align-items: flex-start;
  padding: 36px 0;
}
.logo__label {
  margin-left: 8px;
  font-size: 26px;
  font-weight: bolder;
}
</style>