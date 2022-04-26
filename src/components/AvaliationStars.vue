<template>
  <div class="stars">
    <div v-for="index in 5" :key="index">
      <IosStarOutlineIcon
        v-if="index > avaliation"
        class="iosStar"
        w="24px"
        h="24px"
      />
      <IosStarIcon v-else class="iosStar" w="24px" h="24px" />
    </div>
  </div>
</template>

<script lang="ts">
import IosStarIcon from "vue-ionicons/dist/ios-star.vue";
import IosStarOutlineIcon from "vue-ionicons/dist/ios-star-outline.vue";
export default {
  props: ["avaliation"],
  components: {
    IosStarIcon,
    IosStarOutlineIcon,
  },
};
</script>

<style lang="scss" scoped>
@import "../plugins/theme.scss";
.stars {
  flex: 1;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  .iosStar {
    fill: $primary--500;
  }
}
</style>