<template>
  <nav>
    <div class="burguerlogo">
      <img src="./../assets/burger.png" />
    </div>
    <div class="centeroptions">
      <ul class="ullinks">
        <li>Fazer Meu Pedido</li>
        <li>Cardápio</li>
        <li>Colaboradores</li>
        <li>Sobre</li>
      </ul>
    </div>

    <div class="rightoptions">
      <IconWithBadge icon="user.png" label="Entrar" />
      <IconWithBadge icon="cart.png" :notification="10" />
    </div>
  </nav>
</template>

<script lang="ts">
import IconWithBadge from "./IconWithBadge.vue";
export default {
  return: {
    components: {
      IconWithBadge,
    },
  },
  components: { IconWithBadge },
};
</script>

<style lang="scss" scoped>
@import "../plugins/theme.scss";
nav {
  display: flex;
  width: 100%;
  padding: 0 140px;
  padding-top: 15px;
  .centeroptions,
  .rightoptions {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .centeroptions {
    flex: 1;
  }
  .rightoptions {
    gap: 5px;
  }
}

.ullinks {
  gap: 20px;
  display: inline-flex;
  list-style: none;
  li {
    color: $text-light;
    cursor: pointer;
    transition: all ease-out 300ms;
    position: relative;
    font-size: 1.1rem;
    &::after {
      content: "";
      position: absolute;
      bottom: -5px;
      display: flex;
      width: 80%;
      margin: 0 10%;
      height: 1px;
      background: $primary--400;
      transition: all ease-out 300ms;
      opacity: 0;
    }
    &:hover {
      color: $primary--500;
      &::after {
        opacity: 0.8;
      }
    }
  }
}
</style>