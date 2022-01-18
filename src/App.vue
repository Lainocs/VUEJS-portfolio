<template>
  <Default @active-page="setActivePage">
    <Index v-if="activePage == 1" @active-page="setActivePage" />
    <Projects v-if="activePage == 2" />
    <Contact v-if="activePage == 3" />
    <Cards @active-page="setActivePage" />
  </Default>
</template>

<script>
import Default from './layouts/Default.vue'
import Index from './components/Index.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'
import Cards from './components/includes/Cards.vue'

export default {
  name: 'App',
  components: {
    Default,
    Index,
    Projects,
    Contact,
    Cards
  },
  emits: [
      'activePage'
  ],
  data() {
    return {
      activePage: 2
    }
  },
  methods: {
    setActivePage(id) {
      this.scrollToTop();
      this.activePage = id;
    },
    scrollToTop() {
      window.scrollTo({
        top: 0,
        behavior: 'smooth'
      });
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
