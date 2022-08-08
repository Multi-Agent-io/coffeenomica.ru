<template>
  <section class="hero">
    <div class="hero__img">
      <g-image aria-hidden="true" src="~/assets/images/bg-photo.jpg" alt="Кафе Кофеномика" />
    </div>
    <div class="container hero__container">
      <h1 class="hero__title">
        <span class="hero__sub-title">Первое робокафе в Петербурге</span>
        COFFEENOMICA
        <span class="hero__address">Третье место, Литейный проспект 62</span>
      </h1>
    </div>
  </section>
</template>

<script>
export default {


}
</script>

<style lang="scss" scoped>
  .hero {
    position: relative;
    margin-top: -126px;
    min-height: calc(100vh + 26px);
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: #fff;
    z-index: 1;

    &__container {
      position: relative;
      z-index: 5;
    }

    &__img {
      position: absolute;
      height: 100%;
      width: 100%;
      z-index: 1;

      img {
        height: 100%;
        width: 100%;
      }
    }

    &__title {
      display: flex;
      flex-direction: column;
      align-items: center;
      font-size: 5rem;
      font-family: 'Yeseva One', sans-serif;
      font-weight: normal;
    }

    &__sub-title {
      font-family: 'Roboto Mono', sans-serif;
      font-size: 1.55rem;
      font-weight: 400;
    }

    &__address {
      font-family: 'Roboto Mono', sans-serif;
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

    &__container {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translateX(-50%);
    }

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