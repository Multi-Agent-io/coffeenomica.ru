<template>
  <Layout>

    <!-- Hero block -->
    <Hero/>

    <!-- Robots section (Eisenkoch) -->
    <Section 
      id="robots"
      :description="`Вкусные вафли по${'\u00A0'}фирменным рецептам от${'\u00A0'}робота${'\u2011'}повара Eisenkoch`"
      image="eisenkoch-l.png"
      imageAlt="робот eisenkoch"
      imageText="Посмотреть мультфильм про Айзенкоха"
      link="https://www.youtube.com/watch?v=UKAM6_tFuXk&ab_channel=Multi-AgentSystems"
    >

    <template v-slot:title>
      Робот Eisenkoch готовит вкусные
      <br>
      <span class="title-with-decoration">вафли</span> 
    </template>

    <template v-slot:buttons>

      <g-link class="coffeenomica-section__btn btn" to="https://multi-agent.io/projects/ru/eisenkoch/" aria-label="Узнать про робота пекаря Eisenkoch">
        <span class="btn__text">
          Узнать про <b>Eisenkoch</b>
        </span>
      </g-link>

    </template>


    </Section>

    <!-- Robots section (gaka-chu) -->
    <Section 
      :description="`Интерьер кофейни украшен кистью робота${'\u2011'}художника Gaka${'\u2011'}chu, ещё один повод прийти к${'\u00A0'}нам`"
      image="gakachu-l.png"
      imageAlt="робот gakachu"
      :imageText="`Узнать больше про механического Ван${'\u00A0'}Гога`"
      link="https://www.youtube.com/watch?v=GxlYxaykqTU"
      :isReverse="true"
    >


    <template v-slot:title>
      А&nbsp;робот gaka-chu нарисовал для кафе
      <br>
      <span class="title-with-decoration">картины</span> 
    </template>

    <template v-slot:buttons>

      <g-link class="coffeenomica-section__btn btn" to="https://multi-agent.io/projects/ru/gakachu/" aria-label="Узнать про робота-художника Gaka-chu" >
        <span class="btn__text">
          Узнать про <b>Gaka-chu</b>
        </span>
      </g-link>

    </template>

    </Section>

    <!-- Menu section -->
    <Section 
      id="menu"
      :description="`Угощайтесь вкусными вафлями с${'\u00A0'}топпингами, ароматным кофе и${'\u00A0'}авторскими напитками в${'\u00A0'}первом робокафе Петербурга`"
      image="menu-img.png"
      imageAlt="меню кафе"
      imageText="Ознакомиться с нашим меню"
      link="/menu"
      :withPattern="true"
    >

    <template v-slot:title>
      <br>
      <span class="title-with-decoration">Кофе&nbsp;и&nbsp;вафли</span> 
    </template>

    <template v-slot:buttons>

      <div class="btn-block">
        <g-link class="coffeenomica-section__btn btn" :style="{'marginBottom': '32px'}" to="/menu" aria-label="Посмотреть меню с кофе" target="_blank">
          <span class="btn__text">
            Посмотреть <b>Меню</b>
          </span>
        </g-link>
      </div>

    </template>

    </Section>

  </Layout>
</template>

<script>
export default {

  components: {
    Hero: () => import('~/components/Hero.vue'),
    Section: () => import('~/components/CoffeenomicaSection.vue'),
  },

  metaInfo: {
    title: 'Coffeenomica',
    meta: [
      { key: 'description', name: 'description', content: 'Первое робокафе в Петербурге. Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками' },

      { property: "og:type", content: "website" },
      { property: "og:site_name", content: 'coffeenomica.ru' },
      { property: "og:title", content: 'Coffeenomica' },
      { property: "og:description", content: 'Первое робокафе в Петербурге. Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками' },
      { property: "og:image", content: 'https://coffeenomica.ru/meta-image.jpg' },
      { property: "og:image:width", content: 1280 },
      { property: "og:image:height", content: 718 },
      { property: "og:url", content: 'https://coffeenomica.ru/' },

      { name: "twitter:card", content: "summary_large_image" },
      { name: "twitter:title", content: 'Coffeenomica' },
      { name: "twitter:image", content: 'https://coffeenomica.ru/meta-image.jpg '},
      { name: "twitter:description", content: 'Первое робокафе в Петербурге. Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками' },
    ]
  }
}
</script>

