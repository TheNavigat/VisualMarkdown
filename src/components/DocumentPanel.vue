<template>
  <div>
    <modal name="properties-modal">
      <input type="checkbox" id="checkbox" v-model="el.properties.bold">
      Bold
    </modal>
    <draggable
      class="dragArea list-group documentDrag"
      :list="list2"
      group="markdown"
      @change="log"
    >
      <div
        v-for="element in list2"
        :key="element.id"
        class="list-group-item"
      >
        <div v-if="element.format=='span'" >
          <span @click="show(element)">{{ element.format }} </span>
          <input v-model="element.text" />
        </div>
        <div v-else>
          {{ element.format }} 
          <DocumentPanel :list2="element.children" />
        </div>
          
      </div>
    </draggable>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
    name: 'DocumentPanel',
    components:{
        draggable
    },
    data(){
      return{
        el:{
          properties:{
            bold: false,
            italic: false,
            underline: false
          }
        }
      }
    },
    props: {
      list2: {
        type: Array,
        default: function(){
          return [{

          }]
        }
      }
    },
    methods: {
      log: function(evt) {
        window.console.log(evt);
      },
      show (element) {
        this.el = element
        this.$modal.show('properties-modal');
        console.log(element)
      },
      hide () {
        this.$modal.hide('properties-modal');
      }
    }
}
</script>

<style scoped>
  div {
    background: #479dff;
  }
</style>