<template>
  <div class="scroll-to-top" @click="scrollToTop" v-show="showScrollToTop">
    <i class="fas fa-chevron-up"></i>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showScrollToTop: false,
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.showScrollToTop = window.pageYOffset > 300;
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth',
      });
    },
  },
};
</script>

<style scoped>
.scroll-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 40px;
  height: 40px;
  background-color: rgba(99, 102, 241, 0.7);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: background-color 0.3s;
}

.scroll-to-top:hover {
  background-color: rgba(99, 102, 241, 0.9);
}

.scroll-to-top i {
  color: #fff;
  font-size: 20px;
}
</style>