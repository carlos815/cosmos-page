<template>
  <div class="index-page-content">
    <h3>Welcome to Cosmos</h3>
    <h1>The Internet of Blockchains</h1>
    <p>
      Cosmos is an ever-expanding ecosystem of interconnected apps and services,
      an Interchain built for a decentralized future.
    </p>
    <Visuals />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Visuals from "../components/Visuals.vue";

import "../assets/css/colors/main.scss";

export default Vue.extend({
  name: "IndexPage",
  layout: "home",
  components: { Visuals },
});
</script>

<style lang="scss">
@import "../assets/css/main.scss";

.index-page-content {
  min-height: calc(100vh - $header-height);
  display: flex;
  flex-direction: column;
  place-content: center;

  @include screen-max($screen-phone) {
    align-items: center;
  }
}

h3,
h1,
p {
  margin: 0 0 16px 0;
  z-index: 1;
  position: relative;
}

h3 {
  color: $white-t500;

  @include screen-max($screen-phone) {
    @include title-minus1-overline;
    margin-right: 0;
    text-align: center;
  }
  @include screen-minmax($screen-phone, $screen-tablet) {
    @include title-minus1-overline;
    margin-right: calc(100% - 480px);
  }
  @include screen-minmax($screen-tablet, $screen-biggest) {
    @include title-0-overline;
    margin-right: calc(100% - 480px);
  }
}

h1 {
  color: $white-full;

  @include screen-max($screen-phone) {
    @include title-3-bold;
    margin-right: 0;
    text-align: center;
  }
  @include screen-minmax($screen-phone, $screen-tablet) {
    @include title-4-bold;
    margin-right: calc(100% - 630px);
  }
  @include screen-minmax($screen-tablet, $screen-desktop) {
    @include title-5-bold;
    margin-right: calc(100% - 630px);
  }
  @include screen-min($screen-desktop) {
    @include title-6-bold;
    margin-right: calc(100% - 630px);
  }
}

p {
  color: $white-t800;

  @include screen-max($screen-smallest) {
    @include copy-0-normal;
    text-align: center;
  }
  @include screen-minmax($screen-smallest, $screen-phone) {
    @include copy-0-normal;
    margin-right: 0;
    max-width: 384px;
    text-align: center;
  }
  @include screen-minmax($screen-phone, $screen-tablet) {
    @include copy-0-normal;
    margin-right: calc(100% - 384px);
  }
  @include screen-min($screen-tablet) {
    @include copy-1-normal;
    margin-right: calc(100% - 504px);
  }
}
</style>

