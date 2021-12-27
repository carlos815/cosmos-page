<template>
  <div class="content">
    <Header />
    <Nuxt />
    <Background />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Background from "@/components/Background.vue";

export default { components: { Header, Background } };
</script>

<style lang="scss">
@import "@/assets/css/main.scss";

body {
  min-height: 100vh;
  margin: 0;
  display: flex;
  justify-content: center;
  background-color: $gray-0;
}

body::after {
  content: "";
  display: block;
  position: absolute;
  background-image: linear-gradient(
    to bottom,
    rgba(255, 255, 255, 0) 0,
    $gray-0 100%
  );
  bottom: 0;
  height: 25vw;
  width: 100%;
  z-index: -1;
}

.content {
  min-height: calc(100vh - $header-height);

  @include screen-max($screen-tablet) {
    padding: 0 24px;
  }
  @include screen-minmax($screen-tablet, $screen-desktop) {
    padding: 0 64px;
  }
  @include screen-minmax($screen-desktop, $screen-biggest) {
    margin: 0 96px;
  }
  @include screen-min($screen-biggest) {
    max-width: 1280px;
    padding: 0 96px;
  }
}
</style>
