<template>
  <div class="background">
    <img src="../assets/images/bg.png" />
  </div>
</template>

<script>
export default {};
</script>


<style lang="scss">
@import "@/assets/css/main.scss";

.background {
  position: absolute;
  z-index: -1;
  top: -10vw;
  left: 0;
  right: 0;
  bottom: 0;
  overflow: hidden;
  height: auto;
  img {
    position: relative;

    height: 100%;
    width: 120%;
    left: -20%;
    object-fit: cover;
    @keyframes rotate {
      from {
        transform: rotate(-5deg);
      }
      to {
        transform: rotate(5deg);
      }
    }

    animation-name: rotate;
    animation-duration: 20s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
  }
}

.background::before {
  content: "";
  display: block;
  position: absolute;
  background-image: radial-gradient(transparent, $gray-0);
  bottom: 0;
  height: 100%;
  width: 100%;
  z-index: 10;
}
</style>