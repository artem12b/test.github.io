<script setup>
import { RouterLink, RouterView } from 'vue-router'
import NavBar from "@/components/NavBar.vue";
</script>

<template>
  <div class="wrapper">
    <NavBar/>
    <div class="content">
      <div class="greeting">Hello Evano <span class="wave">👋</span></div>
      <RouterView/>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use '@/assets/scss/mixins/media.scss' as *;

.wrapper {
  display: flex;
  flex-direction: row;

  @include mobile {
    flex-direction: column;
  }
}
.content {
  padding: 41px 95px 76px 71px;
  flex-grow: 1;
  background-color: #FAFBFF;
  max-height: 100vh;

  @include mobile {
    padding: 26px;
    max-height: unset;
  }
}
.greeting {
  font-size: 24px;
  padding-bottom: 51px;

  @include mobile {
    text-align: center;
    padding: 0 0 26px 0;
  }
}
.wave {
  animation-name: wave-animation;
  animation-duration: 2.5s;
  animation-iteration-count: infinite;
  transform-origin: 70% 70%;
  display: inline-block;
}

@keyframes wave-animation {
  0% { transform: rotate( 0.0deg) }
  10% { transform: rotate(14.0deg) }
  20% { transform: rotate(-8.0deg) }
  30% { transform: rotate(14.0deg) }
  40% { transform: rotate(-4.0deg) }
  50% { transform: rotate(10.0deg) }
  60% { transform: rotate( 0.0deg) }
  100% { transform: rotate( 0.0deg) }
}
</style>
