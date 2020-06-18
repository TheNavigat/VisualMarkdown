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
          { format: "H4", id: 4 },
          { format: "H5", id: 5 },
          { format: "H6", id: 6 },
          { format: "B", id: 7 },
          { format: "I", id: 8 },
          { format: "U", id: 9 },
      ],
      list2: [

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
