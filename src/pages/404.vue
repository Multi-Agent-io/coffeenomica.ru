<template>
  <div class="page404">
    <div class="page404__container container">
        <div class="page404__title">
          <!-- упс в двоичном коде -->
          <div>11010001 10000011 11010000 10111111 11010001 10000001!</div>

          <h2> Страница не найдена...</h2>
        </div>
        <p class="page404__text">Пожалуйста, проверьте адрес страницы и попробуйте еще раз</p>
        <g-link class="page404__link link" to="/" aria-label="Перейти на главную страницу">Вернуться на главную страницу</g-link>
    </div>
  </div>
</template>

<script>
export default {
    metaInfo: {
    title: 'Страница не найдена',
    meta: [
      { key: 'description', name: 'description', content: 'Страница не найдена' },
    ]
  }
}
</script>

<style>

  .page404 {
    position: relative;
    min-height: 100vh;
    height: 100%;
  }

  .page404::after {
    content: "";
    position: absolute;
    top: 0; 
    left: 0;
    width: 100%; 
    height: 100%;
    background-image: url('../assets/images/bg-photo.jpg');
    filter: grayscale(100%);
  }

  .page404__container {
    position: relative;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    z-index: 5;
  }

  .page404__title {
    position: relative;
    padding: 30px;
    margin-bottom: 20px;
    color: #fff;;
    background-color: #6d84aa;
    box-shadow: 1px 2px 5px #333;
    border-radius: 10px;
    text-align: center;
    animation: textMove 4s ease-in-out 1.5s infinite;
  }

  .page404__title::after {
    content: '';
    position: absolute;
    right: -4px;
    top: -64%;
    width: 100px;
    height: 100px;
    background-image: url('../assets/images/eisenkoch-transparent.png');
    background-position: center;
    background-size: 100px 100px;
    background-repeat: no-repeat;
    border-radius: 100%;
    transform: scaleX(-1) rotateZ(-10deg);
  }

  .page404__title div {
    position: relative;
    margin-bottom: 5px;
    z-index: 5;
  }

  .page404__text {
    font-size: 12px;
  }

  .page404__link {
    font-weight: 600;
  }

  /* animation for text movement */
  @keyframes textMove
  {
    0%{ transform:rotateZ(0) translate3d(0, 0, 0) scale(1) }
    25%{ transform: translate3d(10px,-25px,10px) }
    50%{ transform:rotateZ(-2deg) translate3d(20px,-20px,23px) scale(0.8)}
    75%{ transform: translate3d(30px,-10px,20px)}
    100%{ transform:rotateZ(0)  translate3d(0px,0px,0px) scale(1)}
  }

  /* styles for media query */
  @media screen and (max-width: 618px) {
    .page404__title::after {
      top: -42%;
    }
  }

</style>