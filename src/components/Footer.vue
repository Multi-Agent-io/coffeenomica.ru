<template>
  <footer id="contacts" class="footer">
    <div class="footer__info footer__info--first">

      <!-- contacts block -->
      <div class="footer__contacts footer__block">
        <h3 class="footer__title">Адрес</h3>
        <address class="footer__address">Санкт-Петербург, Третье место, <br> Литейный проспект 62</address>
        <a href="tel:+79952323781" class="footer__phone">8 (995) 232–37-81</a>
      </div>

      <!-- working hours block -->
      <div class="footer__working-hours footer__block">
        <h3 class="footer__title">Режим Работы</h3>
        <List/>
      </div>

    </div>

    <div class="footer__info footer__info--second">

      <!-- different maps block ? -->
      <div class="footer__maps footer__block">
        <h3 class="footer__title">Посмотреть на картах</h3>
        <g-link class="link footer__link" to="https://go.2gis.com/51wu6">2GIS</g-link>
        <g-link class="link footer__link" to="https://goo.gl/maps/5GQzJtWWah4qF1V47">Google Maps</g-link>
        <g-link class="link footer__link" to="https://yandex.ru/maps/-/CCURa-BpSC">Yandex Карты</g-link>
      </div>

      <!-- collaboration block -->
      <div class="footer__collaboration footer__block">
        <h3 class="footer__title">По вопросам сотрудничества</h3>
        <a class="link" href="mailto:coffeenomica@multi-agent.io">
          coffeenomica@multi-agent.io
        </a>
      </div>

      <!-- Follow block -->
      <div class="footer__follow footer__block">
        <h3 class="footer__title">Подписаться на нас</h3>
        <span class="footer__link">
          @coffeenomica
        </span>
      </div>

    </div>

    <Map/>
  </footer>
</template>

<script>
export default {
  components: {
    Map: () => import('~/components/Map.vue'),
    List: () => import('~/components/ContactsList.vue'),
  }
}
</script>

<style lang="scss">
  .footer {
    position: relative;
    max-height: 800px;
    overflow: hidden;
    &__info {
      position: absolute;
      // top: 0;
      // padding-top: calc(100% * 40 / 1920);
      padding: 40px 0;
      left: 0;
      width: 45%;
      text-align: center;
      z-index: 5;

      &::after {
          content: "";
          position: absolute;
          left: 0;
          top: 0;
          width: 100%;
          height: 100%;
          opacity: .85;
          background-image: url('../assets/images/contacts-overlay.png');
          background-repeat: no-repeat;
          background-position: center;
          background-size: cover; 
          z-index: -1
      }

      &--first {
        top: 0;
        height: 50%;
        z-index: 10;
        // padding-top: calc(100% * 50 / 1920);
      }

      &--second {
        bottom: 0;
        height: 50%;
        // padding-bottom: calc(100% * 50 / 1920);
      }
    }

    &__block {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      font-size: 16px;
      line-height: 24px;
      font-weight: 400;

      &:not(:last-child) {
        margin-bottom: 40px;
      }
    }

    &__title {
      margin-bottom: 10px;
      font-size: 18px;
      font-weight: 600;
      text-transform: uppercase;
      letter-spacing: 0.5px
    }

    &__address {
      margin-bottom: 20px;
      font-style: normal;
    }

    &__item {
      display: flex;
      align-items: center;
      text-align: left;
    }

    &__day {
      font-size: 18px;
      max-width: 32px;
      width: 100%;
    }

    &__time {
      margin-left: 30px;
    }

    &__link {
      &:not(:last-child) {
        margin-bottom: 12px;
      }
    }
  }

  // styles for media queries
  @media screen and (max-width: 932px) {
    .footer {
      min-height: 1094px;
      max-height: unset;
      height: 100%;

      &__info {
        width: 100%;
        position: relative;
        padding: calc(100% * 30 / 900) 0;

        &--second {
          margin-top: 500px;
        }
      }

    }
  }

  @media screen and (max-width: 560px) {

    .footer {
      min-height: auto;

      &__info {
        padding: calc(100% * 30 / 560) 0;

        &--second {
          margin-top: 225px;
        }

      }

      &__title {
        margin-bottom: 20px;
        font-size: 14px;
      }

      &__block {

        &:not(:last-child) {
          margin-bottom: 32px;
        }

        font-size: 14px;
        line-height: 19px;

      }

      &__item {
        white-space: nowrap;
      }

      &__day {
        font-size: 14px;
        max-width: 24px;
      }
    }
  }
</style>