<template>
  <div id="app">
    <div class="help">Drag and drop inside areas with white borders. Put a span block inside any block to insert text.</div>
    <Tools
      :list1="list1"
      class="col-12"
    />
    <DocumentPanel
      :list2="list2"
      class="col-12"
    />

    <PropertiesModal @update:properties="updateProperties"/>
  </div>
</template>

<script>
import './assets/style/core.scss'
import Tools from './components/Tools.vue'
import DocumentPanel from './components/DocumentPanel.vue'
import PropertiesModal from './components/PropertiesModal'

export default {
  name: 'App',
  components: {
    Tools,
    DocumentPanel,
    PropertiesModal
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
          { format: "span", id: 19 },

      ],
      list2: [

      ]
    }
  },
  methods:{
    updateProperties(id, updatedElement){
      // console.log(id)
      // this.list2 = 
      this.list2 = (function upd(data, newData) {
          return data.map(element => {
              if (element.children) {
                  var o = element
                  o.children = upd(element.children, newData);
                  return o;
              }
              else if (element.id === id) {
                  return newData;
              } else return element;
          });
      })(this.list2, updatedElement);
      // this.list2 = this.list2.map(item =>{
      //   // console.log(item.id, id, item, updatedElement);
      //   if(item.id===id){
      //     item = updatedElement;
      //   }
      //   return item;
      // })
      console.log(this.list2)
    }
  }
}
</script>

<style>
#app {
  text-align: center;
}
</style>
