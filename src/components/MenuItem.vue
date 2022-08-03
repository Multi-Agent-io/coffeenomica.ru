<template>
  <div class="menu__info">
    <div class="menu__info-top">
      <h3 class="menu__sub-title">{{option.title}}</h3>
      <span class="menu__price">{{option.price}}</span>
    </div>

    <p v-if="option.description" class="menu__descr">({{option.description && option.description}})</p>

    <g-image v-if="option.img" :src="require(`!!assets-loader!@images/${option.img}`)" :alt="option.title" />
  </div>
</template>

<script>
export default {
  props: {
    option: {
      type: Object,
      required: true,
      default: null,
    }
  }

}
</script>

<style lang="scss" >
</style>