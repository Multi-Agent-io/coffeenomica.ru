<template>
  <li class="footer__item">
    <span class="footer__day">{{day}}</span>
    <span class="footer__time">{{time}}</span>
  </li>
</template>

<script>
export default {
  props: {

    day: {
      type: String,
      required: true,
    },

    time: {
      type: String,
      default: "11:00 - 22:00"
    }
  }

}
</script>

<style>

</style>