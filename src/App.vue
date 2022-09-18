<template>
  <div id="app">
    <div class="row">
      <HeaderComponent />
    </div>
    <ContentComponent :content="content" />
  </div>
</template>

<script>
  import axios from 'axios';
  import HeaderComponent from './components/HeaderComponent.vue';
  import ContentComponent from './components/ContentComponent.vue';
  import { defineCustomElement } from 'vue'
  import TableComponent from '@/components/ContentComponents/TableComponent.vue'

  export default {
    name: 'App',
    components: {
      HeaderComponent,
      ContentComponent
    }, 
    data() {
      return {
        content: ['title', 'content']
      }
    },
    created: function() {
      axios.get('http://localhost:8000/api/content' + window.location.pathname)
        .then(res=> {
          this.content = res.data
      }).then(function() {        
        const Graph = defineCustomElement(TableComponent)

        customElements.define('skill-graph', Graph)
      })
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
