<template>
  <section class="banner">
    <NavBar />
    <BannerFood />
    <SocialMedia />
  </section>
</template>

<script lang="ts">
import NavBar from "../components/NavBar.vue";
import BannerFood from "../components/BannerFood.vue";
import SocialMedia from "../components/SocialMedia.vue";
export default {
  components: {
    NavBar,
    BannerFood,
    SocialMedia,
  },
};
</script>

<style lang="scss">
@import "../plugins/theme.scss";
.banner {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  background-position: center;
  background-size: cover;
  background-image: radial-gradient(
      circle,
      transparent 0%,
      $dark--100-rgba-90 90%
    ),
    url("../assets/wood-bg.jpg");
}

.socialmedia {
  position: absolute !important;
  bottom: 50px;
  right: 150px;
}
</style>