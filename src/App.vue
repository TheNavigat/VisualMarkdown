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
          { text:"", format: "H1", id: 1 },
          { text:"", format: "H2", id: 2 },
          { text:"", format: "H3", id: 3 },
          { text:"", format: "H4", id: 4 }
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
