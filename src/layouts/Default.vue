<template>
  <div class="layout">

    <Header/>

    <main>
      <slot/>
    </main>

    <Footer/>

  </div>
</template>


<script>
  export default {
    components: {
      Header: () => import('~/components/Header.vue'),
      Footer: () => import('~/components/Footer.vue'),
    }
  }
</script>
