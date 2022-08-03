<template>
  <section class="hero">
    <div class="container">
      <h3 class="hero__sub-title">Первое робокафе в Петербурге</h3>
      <h1 class="hero__title">COFFEENOMICA</h1>
      <address class="hero__address">Третье место, Литейный проспект 62</address>
    </div>
  </section>
</template>

<script>
export default {


}
</script>

<style lang="scss" scoped>
  .hero {
    margin-top: -126px;
    min-height: calc(100vh + 26px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: #fff;
    background-image: url('../assets/images/bg-photo.jpg');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    &__title {
      font-size: 5rem;
      font-family: 'Yeseva One', sans-serif;
      font-weight: normal;
      text-transform: uppercase;
    }

    &__sub-title {
      font-size: 1.55rem;
      font-weight: 400;
    }

    &__address {
      font-size: 1rem;
      line-height: 29px;
      font-style: normal;
    }
  }

  // styles for media queries

  @media screen and (max-width: 900px) {

    .hero {
      &__title {
        font-size: 3rem;
      }

      &__sub-title {
        font-size: 1rem;
      }

      &__address {
        font-size: 0.8rem;
      }

    }
  }

  @media screen and (max-width: 560px) {
    .hero {
      &__title {
        font-size: 36px;
        line-height: 43px;
      }

      &__sub-title {
        font-size: 16px;
        line-height: 24px;
      }

      &__address {
        font-size: 14px;
        line-height: 19px;
      }

    }
  }
</style>