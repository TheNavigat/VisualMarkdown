<template>
  <draggable
    class="dragArea list-group"
    :list="list2"
    group="markdown"
    @change="log"
  >
    <div
      v-for="element in list2"
      :key="element.id"
      class="list-group-item"
    >
      {{ element.format }} 
      <input v-model="element.text">
    </div>
  </draggable>
</template>

<script>
import draggable from "vuedraggable";

export default {
    name: 'DocumentPanel',
    components:{
        draggable
    },
    props: {
      list2: {
        type: Array,
        default: function(){
          return [{}]
        }
      }
    },
    methods: {
      log: function(evt) {
        window.console.log(evt);
      }
    }
}
</script>

<style scoped>
  div {
    background: #479dff;
  }
</style>