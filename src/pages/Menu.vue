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
  <!-- <div class="menu" v-if="menu">

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

    <div class="menu__container menu__container--special">
      <div v-for="item in special" :key="item.id" class="menu__wrapper">
        <MenuBlock :category=item.category :options=item.options :addsOn="item.additional" />
      </div>
    </div>

  </div> -->
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
    title: 'Меню Кофеномики',
    meta: [
      { key: 'description', name: 'description', content: 'Кофеномика - меню кафе' },
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
