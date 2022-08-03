<template>
  <ul class="menu__list" v-if="options">
    <li class="menu__item" v-for="option in options" :key="option.id">
      <MenuItem :option="option"/>
    </li>
    <div class="menu__adds-on" v-if="addsOn">
      <ul class="menu__list">
        <li class="menu__item" v-for="addOn in addsOn" :key="addOn.id">
            <MenuItem :option="addOn"/>
        </li>
      </ul>
    </div>
  </ul>
</template>

<script>
export default {

  components: {
    MenuItem: () => import('~/components/MenuItem.vue'),
  },

  props: {
    options: {
      type: Array, 
      default: () => [],
    },

    addsOn: {
      type: Array, 
      default: () => [],
    }
  }

}
</script>

<style lang="scss">

</style>