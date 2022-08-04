<template>
  <header class="header">
    <div class="container header__container">

      <g-link class="logo header__logo" to="/">
        <g-image src="@/assets/images/logo.svg" alt="логотип Coffeenomica" />
      </g-link>

      <!-- burger button -->

      <button @click="isMenuOpen = !isMenuOpen" tabindex="0" class="burger" aria-label="Открыть меню сайта" :class="{'active': isMenuOpen}">
        <span class="burger-line"></span>
        <span class="burger-line"></span>
        <span class="burger-line"></span>
      </button>


      <div class="mobile-menu" :class="{'active': isMenuOpen}">

        <nav id="nav" class="nav">
          <ul class="nav__list">
            <li class="nav__item">
              <a class="nav__link link" aria-label="Узнать больше о наших чудо-роботах" href="#robots" @click="(e) => scrollToSection(e, 'robots') ">Роботы</a>
            </li>
            <li class="nav__item">
              <a class="nav__link link" aria-label="Узнать больше о меню меню" href="#menu"  @click="(e) => scrollToSection(e, 'menu')">Меню</a>
            </li>
            <li class="nav__item">
              <a class="nav__link link" href="#contacts" aria-label="Узнать где мы находимся" @click="(e) => scrollToSection(e, 'contacts')">Контакты</a>
            </li>
          </ul>
        </nav>

        <div class="header__contacts">
          <a href="tel:+79952323781" class="header__phone">8 (995) 232–37-81</a>
          <span class="header__link">@coffeenomica</span>
        </div>

      </div>

    </div>
  </header>
</template>

<script>
export default {

  data() {
    return {
      isMenuOpen: false,
    }
  },

  methods: {
    scrollToSection(e,el) {
      this.isMenuOpen = false;

      if (e) {
        e.preventDefault();
      }

      const element = document.querySelector(`#${el}`);
      const location = window.location.toString().split('#')[0];

      history.replaceState(null, null, location + '#' + el);


      if(element) {
        element.scrollIntoView({ behavior: "smooth" });
      }
    }
  },

  mounted() {
    if(this.$route.hash) {
      setTimeout(() => this.scrollToSection(null, this.$route.hash.substring(1)), 300)
    }

  }


}
</script>

<style lang="scss">

  $color-light: #ffffff;

  .header {
    padding-top: 26px;

    &__container {
      position: relative;
      display: flex;
      align-items: center;
      z-index: 5;
    }

    &__logo {
      display: inline-block;
      margin-right: 92px;

      img {
        width: 120px;
        height: 75px;
      }
    }

    &__phone,
    &__link {
      font-size: 21px;
      font-weight: 600;
      line-height: 28px;
      color: $color-light;
      text-transform: uppercase;
    }

    &__phone {
      margin-right: 75px;
    }

  }

  .nav {
    margin-right: auto;

    &__list {
      display: flex;
      align-items: center;
    }

    &__item {
      &:not(:last-child) {
        margin-right: 107px;
      }
    }

    &__link {
      font-size: 21px;
      font-weight: 600;
      line-height: 28px;
      text-transform: uppercase;

    }
  }

  .mobile-menu {
    display: flex;
    width: 100%;
  }

  .burger {
    display: none;
  }

  // styles for media queries
  @media screen and (max-width: 1300px) {

    .header {
      &__logo,
      &__phone {
        margin-right: 40px;
      }

      &__phone,
      &__link {
        font-size: 16px;
      }
    }

    .nav {
      &__item {
        &:not(:last-child) {
          margin-right: 30px;
        }
      }

      &__link {
        font-size: 16px;
      }
    }
  }

  @media screen and (max-width: 900px) {
    .header {
      position: relative;
      padding-top: 10px;

      &__logo {
        margin-right: auto;

        img {
          width: 60px;
          height: 45px;
        }
      }

      &__contacts {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      &__phone {
        margin-right: 0;
        margin-bottom: 20px;
        font-size: 1rem;
      }

      &__link {
        font-size: 1rem;
      }
    }

      .burger {
        display: block;
        z-index: 30;
      }

    .mobile-menu {
      position: fixed;
      padding-top: 80px;
      width: 100%;
      top: 0;
      bottom: 0;
      left: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background-image: url('../assets/images/background-blue.jpg');
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
      transform: translateX(-110%);
      transition: transform 0.4s ease-in-out, opacity 0.33s ease-in-out, visibility 0.4s ease;
      opacity: 0;
      z-index: 20;
      visibility: hidden;

      &.active {
        opacity: 1;
        visibility: visible;
        transform: translateX(0%);
      }
    }

    .nav {
      margin-right: 0;

      
      &__list {
        flex-direction: column;
      }

      &__item {

        &:not(:last-child) {
          margin-bottom: 45px;
          margin-right: 0;
        }

        &:last-child {
          margin-bottom: 70px;
        }
      }

      &__link {
        font-size: 2rem;
      }
    }

  }

  @media screen and (max-width: 560px) {
    .header {
      position: fixed;
      top: 0;
      left: 0;
      padding-bottom: 15px;
      width: 100%;
      // height: 100%;
      z-index: 20;

      &::after {
        content: '';
        position: absolute;
        top: -5px;
        left: 0;
        width: 100%;
        height: 100%;
        background:  url('../assets/images/background-blue.jpg');
        // background:  url('../assets/images/header-mobile-bg.png');
        background-position: center;
        background-size: cover;
        // filter: blur(3px);
        z-index: 10;
        // opacity: 0.4 ;
      }

      &__container {
        z-index: 20;
      }
    }


    .nav__link {
      font-size: 1rem;
    }

    .mobile-menu {
      padding-top: 0;
    }

    .burger {
      top: 16px;
    }
  }
</style>