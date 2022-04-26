
<script lang="ts">
export default {
  props: ["icon", "label", "notification"],
};
</script>

<template>
  <button>
    <strong v-if="label">{{ label }}</strong>
    <img :src="`src/assets/${icon}`" />
    <span class="bagde" v-if="notification">{{
      notification > 9 ? "9+" : notification
    }}</span>
  </button>
</template>

<style lang="scss" scoped>
@import "../plugins/theme.scss";
button {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  cursor: pointer;
  background: transparent;
  outline: none;
  border: none;
  position: relative;
  strong {
    color: $background-light-1000;
  }
  img {
    width: 25px;
    resize: both;
  }
  .bagde {
    position: absolute;
    display: block;
    color: $background-light-1000;
    top: -0.5rem;
    right: -0.5rem;
    font-size: 0.6rem;
    background: $danger;
    min-width: 15px;
    min-height: 15px;
    padding: 2px;
    border-radius: 8px;
  }
}
</style>