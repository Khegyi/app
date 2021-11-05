<template>
  <div id="app">
    <div class="dark-hero-bg">
      <p class="dark-hero-text">CHRISTOPHER WARD</p>
    </div>
    <Header />
    <Content />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Content from "./components/Content.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Content,
    Footer,
  },
};
</script>

<style lang="scss">
@import "./styles/index.scss";
</style>
