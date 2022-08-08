<template>
      <transition name="fade" appear>
        <div class="menu" v-if="menu">

          <div class="menu__container menu__container--coffee">
            <div v-for="item in coffee" :key="item.id" class="menu__wrapper">
              <MenuBlock :category=item.category :options=item.options :addsOn="item.additional" />
            </div>
          </div>

          <div class="menu__container menu__container--waffles">
            <div v-for="item in waffles" :key="item.id" class="menu__wrapper">
              <MenuBlock :category=item.category :options=item.options :addsOn="item.additional" />
            </div>
          </div>

          <div class="menu__container menu__container--smoothies">
            <div v-for="item in smoothie" :key="item.id" class="menu__wrapper">
              <MenuBlock :category=item.category :options=item.options :addsOn="item.additional" />
            </div>
          </div>

          <div class="menu__container menu__container--lemonades">
            <div v-for="item in lemonades" :key="item.id" class="menu__wrapper">
              <MenuBlock :category=item.category :options=item.options :addsOn="item.additional" />
            </div>
          </div>

          <div class="menu__container menu__container--special">
            <div v-for="item in special" :key="item.id" class="menu__wrapper">
              <MenuBlock :category=item.category :options=item.options :addsOn="item.additional" />
            </div>
          </div>

        </div>
      </transition>
</template>

<script>
  import menu from '@/data/menu.yaml'
export default {
  components: {
    MenuBlock: () => import('~/components/MenuBlock.vue'),
  },

  computed: {
    menu () {
      return menu
    },

    smoothie() {
      return menu.filter(item => item.category.toLowerCase() === 'смузи' || item.category.toLowerCase() === 'холодняк')
    },

    waffles() {
      return menu.filter(item => item.category.toLowerCase() === 'вафли')
    },

    lemonades() {
      return menu.filter(item => item.category.toLowerCase() === 'baza' || item.category.toLowerCase() === 'лимонады')
    },

    coffee() {
      return menu.filter(item => item.category.toLowerCase() === 'черный' || item.category.toLowerCase() === 'с молоком' || item.category.toLowerCase() === 'не кофе')
    },

    special() {
      return menu.filter(item => item.category.toLowerCase() === 'спешл недели')
    }

  },


  metaInfo: {
    title: 'Меню Coffeenomica',
    meta: [
      { key: 'description', name: 'description', content: 'Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками в первом робокафе Петербурга' },

      { property: "og:type", content: "website" },
      { property: "og:site_name", content: 'coffeenomica.ru' },
      { property: "og:title", content: 'Меню Coffeenomica' },
      { property: "og:description", content: 'Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками в первом робокафе Петербурга' },
      { property: "og:image", content: 'https://coffeenomica.ru/meta-image.jpg' },
      { property: "og:image:width", content: 1280 },
      { property: "og:image:height", content: 718 },
      { property: "og:url", content: 'https://coffeenomica.ru/' },

      { name: "twitter:card", content: "summary_large_image" },
      { name: "twitter:title", content: 'Меню Coffeenomica ' },
      { name: "twitter:image", content: 'https://coffeenomica.ru/meta-image.jpg '},
      { name: "twitter:description", content: 'Первое робокафе в Петербурге. Угощайтесь вкусными вафлями с топпингами, ароматным кофе и авторскими напитками' },
    ]
  }

}
</script>

<style lang="scss">
  .fade-enter-active {
    transition: opacity .8s;
  }

  .fade-enter {
    opacity: 0;
  }
</style>>
