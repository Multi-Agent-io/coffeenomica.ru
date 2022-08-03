<template>
  <div class="menu-title">
    <h2 class="menu-title__text">
      {{title}}
    </h2>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    }
  }

}
</script>

<style lang="scss">

</style>>
