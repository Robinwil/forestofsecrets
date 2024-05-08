<template>
  <div id="app">
    <navigation-menu />

    <div class="mx-auto">
      <transition name="fade" mode="out-in">
        <router-view />
      </transition>
    </div>

    <scroll-to-top />

    <footer-component />
  </div>
</template>

<script>
import NavigationMenu from '@/components/NavigationMenu.vue';
import ScrollToTop from '@/components/ScrollToTop.vue';
import FooterComponent from '@/components/Footer.vue';

export default {
  components: {
    NavigationMenu,
    ScrollToTop,
    FooterComponent,
  },
};
</script>

<style>
html {
  scroll-behavior: smooth;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>