<template>
  <div id="app">
    <Tools
      :list1="list1"
      class="col-12"
    />
    <DocumentPanel
      :list2="list2"
      class="col-12"
    />
  </div>
</template>

<script>
import './assets/style/core.scss'
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
          { format: "h1", id: 1 },
          { format: "h2", id: 2 },
          { format: "h3", id: 3 },
          { format: "h4", id: 4 },
          { format: "h5", id: 5 },
          { format: "h6", id: 6 },
          // { format: "b", id: 7 },
          // { format: "i", id: 8 },
          // { format: "u", id: 9 },
          // { format: "code", id: 10 },
          // { format: "image", id: 11 },
          // { format: "hyperlink", id: 12 },
          { format: "paragraph", id: 13 },
          // { format: "numbered-list", id: 14 },
          // { format: "bullets-list", id: 15 },
          // { format: "block-quote", id: 16 },
          // { format: "fenced-code-block", id: 17 },
          // { format: "horizontal-rule", id: 18 },
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
}
</style>
