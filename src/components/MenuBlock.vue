<template>
  <div class="menu__block">
    <MenuTitle :title="category" />
    <MenuList :options="options" :addsOn="addsOn" />
  </div>
</template>

<script>

export default {

  components: {
    MenuTitle: () => import('~/components/MenuTitle.vue'),
    MenuList: () => import('~/components/MenuList.vue'),
  },

  props: {
    category: {
      type: String,
      required: true
    },

    options: {
      type: Array,
      required: true
    },

    addsOn: {
      type: Array,
    }
  }

}
</script>

<style lang="scss">
</style>>
