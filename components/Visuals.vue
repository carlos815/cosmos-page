<template>
  <div class="visuals-wrapper">
    <div class="visuals"><img src="../assets/images/visuals.svg" /></div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "@/assets/css/main.scss";

.visuals-wrapper {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  overflow: hidden;

  display: flex;
  place-content: center;

  .visuals {
    position: absolute;
    margin: 12px;

    img {
      width: 100%;
    }

    @include screen-max($screen-smallest) {
    }
    @include screen-minmax($screen-smallest, $screen-phone) {
      height: 100vh;
      max-height: 416px;
      width: 100vh;
      max-width: 416px;
    }

    @include screen-minmax($screen-phone, $screen-tablet) {
      max-height: 552px;
      height: 100vh;
      width: 100vh;
      max-width: 552px;

      top: 0;
      right: -8%;
      transform: translate(0%, 0);
    }

    @include screen-minmax($screen-tablet, $screen-desktop) {
      max-height: 552px;
      height: 100vh;
      max-width: 552px;
      width: 100vh;

      top: 0;
      right: 0%;
      transform: translate(0%, 0);
    }

    @include screen-minmax($screen-desktop, $screen-biggest) {
      max-height: 744px;
      height: 100vh;
      max-width: 744px;
      width: 100vh;

      top: 0;
      right: 3%;
      transform: translate(0%, 0);
    }

    @include screen-min($screen-biggest) {
      max-height: 840px;
      height: 100vh;
      max-width: 840px;
      width: 100vh;

      top: 0;
      right: 12%;
      transform: translate(0%, 0);
    }
  }
}
</style>