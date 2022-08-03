<template>
  <Layout>

    <!-- Hero block -->
    <Hero/>

    <!-- Robots section (Eisenkoch) -->
    <Section 
      id="robots"
      title="Робот Eisenkoch готовит вкусные"
      titleWithDecoration="вафли"
      description="Вкусные вафли по фирменным рецептам от робота-повора Eisenkoch"
      image="eisenkoch.png"
      imageAlt="робот eisenkoch"
      imageText="Посмотреть мультфильм про Айзенкоха"
      link="https://www.youtube.com/watch?v=UKAM6_tFuXk&ab_channel=Multi-AgentSystems"
    >

      <g-link class="coffeenomica-section__btn btn" to="https://multi-agent.io/projects/ru/eisenkoch/" aria-label="Узнать про робота-пекаря Eisenkoch">
        <span class="btn__text">
          Узнать про <b>Eisenkoch</b>
        </span>
      </g-link>

    </Section>

    <!-- Robots section (gaka-chu) -->
    <Section 
      title="А робот gaka-chu нарисовал для кафе"
      titleWithDecoration="картины"
      description="Интерьер кофейни украшен кистью робота-художника Gaka-chu, ещё один повод прийти к нам"
      image="gakachu.png"
      imageAlt="робот gakachu"
      :isReverse="true"
    >

      <g-link class="coffeenomica-section__btn btn" to="https://multi-agent.io/projects/ru/gakachu/" aria-label="Узнать про робота-художника Gaka-chu" >
        <span class="btn__text">
          Узнать про <b>Gaka-chu</b>
        </span>
      </g-link>

    </Section>

    <!-- Menu section -->
    <Section 
      id="menu"
      titleWithDecoration="Кофе и вафли"
      :description="`Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками в первом робокафе Петербурга` "
      image="menu-img.png"
      imageAlt="меню кафе"
      :withPattern="true"
    >

      <div class="btn-block">
        <g-link class="coffeenomica-section__btn btn" :style="{'marginBottom': '32px'}" to="/menu" aria-label="Посмотреть меню с кофе">
          <span class="btn__text">
            Меню с <b>КОФЕ</b>
          </span>
        </g-link>
        <g-link class="coffeenomica-section__btn btn" to="/menu" aria-label="Посмотреть меню с вафлями">
          <span class="btn__text">
            Меню с <b>ВАФЛЯМИ</b>
          </span>
        </g-link>
      </div>

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
    title: 'Главная',
    meta: [
      { key: 'description', name: 'description', content: 'Кофеномика - главная страница' },
    ]
  }
}
</script>

