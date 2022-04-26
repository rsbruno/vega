<template>
  <section class="socialmedia">
    <a href="/">
      <img src="../assets/facebook.png" alt="logo facebook" />
    </a>
    <a href="/">
      <img src="../assets/instagram.png" alt="logo instagram" />
    </a>
    <a href="/">
      <img src="../assets/whatsapp.png" alt="logo whatsapp" />
    </a>
  </section>
</template>

<style lang="scss" scoped>
.socialmedia {
  display: flex;
  gap: 8px;
  flex-direction: column;
  a {
    img {
      width: 28px;
      background-size: cover;
    }
  }
}
</style>