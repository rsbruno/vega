<script lang="ts">
import AvaliationStars from "./AvaliationStars.vue";
export default {
  props: ["data", "title", "price"],
  components: {
    AvaliationStars,
  },
};
</script>

<template>
  <section class="container">
    <div class="containerfood">
      <img
        :src="`src/assets/${data.foodImg}`"
        :alt="`imagem de um(a) ${data.title}`"
      />
      <div class="foodname">
        <h1>{{ data.title }}</h1>
      </div>
      <div class="foodprice">
        <h3><b>R$</b>{{ data.price }}</h3>
      </div>
    </div>

    <div class="infos">
      <section class="content">
        <div class="description">
          <div class="title">
            <h6>{{ data.descriptionTitle }}</h6>
            <AvaliationStars :avaliation="data.avaliation" />
          </div>
          <p>{{ data.descriptionBody }}</p>
          <button>Adicionar na Comanda</button>
        </div>
      </section>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../plugins/theme.scss";

.container {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: center;
  padding-top: 5%;
  .containerfood {
    width: 480px;
    height: 460px;
    position: relative;
    img {
      width: 100%;
      background-size: cover;
    }
    .foodname {
      width: 100%;
      position: absolute;
      bottom: -1rem;
      h1 {
        color: #fff;
        font-family: $text-emphasis, sans-serif;
        text-transform: uppercase;
        font-size: 3rem;
        transform: scale(3, 4);
        text-shadow: $dark--500 1px 0 10px;
        text-align: center;
      }
    }
    .foodprice {
      width: auto;
      height: auto;
      background: $danger;
      position: absolute;
      top: 0;
      right: 0;
      padding: 8px 12px;
      border-top-right-radius: 15px;
      border-bottom-left-radius: 15px;
      h3 {
        color: #fff;
        font-family: $text-cursive;
        font-size: 1.5rem;
        b {
          font-family: $text-siple-2;
          margin-right: 4px;
          font-size: 1rem;
        }
      }
    }
  }
  .infos {
    height: 460px;
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    flex-direction: column;
    .content {
      display: flex;
      align-items: flex-start;
      justify-content: flex-end;
      flex-direction: column;
      margin-left: 40px;
      margin-bottom: 130px;
      .description {
        z-index: 5;
        h6 {
          color: $primary--400;
          font: normal 2.7rem $text-cursive;
          font-weight: 800;
        }
        p {
          width: 300px;
          color: #fff;
          font-weight: 300;
          font-size: 0.9rem;
          margin: 20px 0;
        }
        button {
          height: 52px;
          background: $chocolate-web--400;
          border: solid 3px $chocolate-web--500;
          outline: none;
          border-radius: 5px;
          color: $text-light;
          padding: 0 12px;
          font: normal 1.1rem $text-cursive;
          cursor: pointer;
          transition: all ease-out 300ms;
          &:hover {
            background: $chocolate-web--500;
          }
          &:active {
            transform: scale(0.99);
          }
        }
        .title {
          display: flex;
          justify-content: center;
          align-items: flex-start;
          flex-direction: column;
          position: relative;
          padding-left: 10px;
          &::before {
            content: "";
            display: block;
            width: 5px;
            height: 100%;
            background: $primary--400;
            position: absolute;
            left: 0;
            border-radius: 5px;
          }
          .stars {
            margin-top: -8px;
          }
        }
      }
    }
  }
}
</style>