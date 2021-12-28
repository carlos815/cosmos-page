<template>
  <div class="header">
    <div v-show="!isMobile" class="full-nav">
      <div class="logo"><img src="../assets/images/cosmos-logo.svg" /></div>
      <ul>
        <li><router-link to="/learn">Learn</router-link></li>
        <li><router-link to="/build">Build</router-link></li>
        <li><router-link to="/explore">Explore</router-link></li>
      </ul>

      <router-link to="/Start" class="call-to-action"> Start Now </router-link>
    </div>

    <div v-show="isMobile" class="mobile-nav">
      <div class="logo"><img src="../assets/images/cosmos-logo.svg" /></div>

      <ul v-show="isNavMenuOpen">
        <li><router-link to="/learn">Learn</router-link></li>
        <li><router-link to="/build">Build</router-link></li>
        <li><router-link to="/explore">Explore</router-link></li>
        <li>
          <router-link to="/learn"
            >No design for this but the functionality is there 😁</router-link
          >
        </li>
      </ul>

      <button class="nav-btn-menu" @click="toggleNavMenu">
        <img src="../assets/images/menu-icon.svg" />
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isNavMenuOpen: false,
      isMobile: true,
      windowWidth: null,
    };
  },

  mounted() {
    window.onresize = this.checkScreenSize;
    this.checkScreenSize();
  },

  methods: {
    toggleNavMenu: function () {
      this.isNavMenuOpen = !this.isNavMenuOpen;
    },

    checkScreenSize: function () {
      this.windowWidth = window.outerWidth;

      if (this.windowWidth < 320) {
        this.isMobile = true;
        return;
      }

      this.isMobile = false;
      this.isNavMenuOpen = false;
    },
  },
};
</script>


<style lang="scss">
@import "@/assets/css/main.scss";

.header {
  z-index: 10;
  position: relative;

  .full-nav {
    display: flex;
    min-height: $header-height;
    align-items: center;

    .logo {
      margin-right: auto;
      margin-left: 0;
    }

    ul {
      padding: 0;
      list-style-type: none;
      display: flex;

      li {
        margin: 0 16px;
      }

      li a {
        text-decoration: none;
        @include solid-minus1-medium;
        color: $white-full;
      }
    }

    .call-to-action {
      margin-left: auto;
      margin-right: 0;
      padding: 12px 24px;
      background-color: $white-t800;
      border-radius: 6px;

      @include solid-minus1-medium;
      text-decoration: none;
      color: $gray-0;
    }
  }

  .mobile-nav {
    display: flex;
    align-items: center;
    height: 64px;

    .nav-btn-menu {
      margin-left: auto;
      background: transparent;
      border: none;
    }
  }
}
</style>