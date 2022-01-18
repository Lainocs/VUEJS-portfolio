<template>
  <div id="screen" :style="{ backgroundImage: 'url(' + require('@/assets/images/background.jpg') + ')' }">
    <Navbar @active-page="setActivePage" />
    <slot></slot>
  </div>
</template>

<script>
  import Navbar from './includes/Navbar.vue'
  export default {
    name: 'default',
    components: {
      Navbar
    },
    methods: {
      setActivePage(id) {
        this.$emit('active-page', id);
      }
    },
  }
</script>

<style lang="scss">
  #screen {
    min-height: 100vh;
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    position: relative;
    overflow-x: hidden;
  }

  h1 {
    color: #fff;
  }
</style>