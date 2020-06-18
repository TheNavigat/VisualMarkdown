<template>
  <div id="app">
    <div>Welcome to Visual Markdown</div>
    <Tools v-bind:list1="list1" class="col-6"/>
    <DocumentPanel v-bind:list2="list2" class="col-6"/>
  </div>
</template>

<script>
import Tools from './components/Tools.vue'
import DocumentPanel from './components/DocumentPanel.vue'

export default {
  name: 'App',
  components: {
    Tools,
    DocumentPanel
  },
  data(){
    return{
      list1: [
          { format: "H1", id: 1 },
          { format: "H2", id: 2 },
          { format: "H3", id: 3 },
          { format: "H4", id: 4 }
      ],
      list2: [
          { format: "Juan", id: 5 },
          { format: "Edgard", id: 6 },
          { format: "Johnson", id: 7 }
      ]
    }
  }
}
</script>

<style>
#app {
  text-align: center;
  margin-top: 60px;
}
</style>
