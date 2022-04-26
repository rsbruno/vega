<script lang="ts">
import FoodApresentation from "./FoodApresentation.vue";
import foodsMock from "../mocks/landing.json";
export default {
  data() {
    return {
      foodsMock,
    };
  },
  components: {
    FoodApresentation,
  },
};
</script>

<template>
  <section>
    <div class="containermain" v-for="food in foodsMock" :key="food.uuid">
      <FoodApresentation :data="food" title="x-burger" price="22,99" />
    </div>
    <nav v-if="foodsMock.length > 1">
      <ul v-for="food in foodsMock" :key="food.uuid">
        <li></li>
      </ul>
    </nav>
  </section>
</template>

<style lang="scss" scoped>
@import "../plugins/theme.scss";
section {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  nav {
    padding: 50px 0;
    ul {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 20px;
      li {
        gap: 15px;
        width: 65px;
        height: 3px;
        border-radius: 999999px;
        background: $background-light-1000;
        list-style: none;
        cursor: pointer;
      }
    }
  }

  .containermain {
    width: 80%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: flex-start;
  }
}
</style>