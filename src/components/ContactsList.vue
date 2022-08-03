<template>
  <ul class="footer__list">
    <Item  v-for="item in working_hours" :key="item.id" :day="item.day" :time="item.time"/>
  </ul>
</template>

<script>
    import working_hours from '@/data/working_hours.yaml'
export default {
  components: {
    Item: () => import('~/components/ContactsItem.vue'),
  },

  computed: {
    working_hours() {
      return working_hours
    }
  }
}
</script>

<style>

</style>