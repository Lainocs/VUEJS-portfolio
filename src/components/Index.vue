<template>
    <div>
        <Presentation />
        <About />
        <Skills />
        <Projects @active-page="setActivePage" />
    </div>
</template>

<script>
import Presentation from './includes/Presentation.vue'
import About from './includes/About.vue'
import Projects from './includes/Projects.vue'
import Skills from './includes/Skills.vue'

export default {
  name: 'App',
  components: {
    Presentation,
    About,
    Projects,
    Skills,
  },
  methods: {
    setActivePage(id) {
      this.$emit('active-page', id);
    }
  },
}
</script>

<style lang="scss">
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
