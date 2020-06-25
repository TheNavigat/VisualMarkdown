<template>
  <div>
    <draggable
      class="dragArea list-group"
      :list="list1"
      :group="{ name: 'markdown', pull: 'clone', put: false }"
      :clone="cloneMethod"
      @change="log"
    >
      <span
        v-for="element in list1"
        :key="element.id"
        class="list-group-item"
      >
        <button>
          <ComponentButton :format="element.format" />
        </button>
      </span>
    </draggable>
  </div>
</template>

<script>
import draggable from "vuedraggable";
import ComponentButton from "./ComponentButton.vue"
let idGlobal = 19;

export default {
    name: 'Tools',
    components:{
        draggable,
        ComponentButton
    },
    props:{
      list1: {
        type: Array,
      }
    },
    methods: {
      log: function(evt) {
        window.console.log(evt);
      },
      cloneMethod({format}){
        return {
          id: idGlobal++,
          format: format  
        };
      }
    }
}
</script>

<style scoped>

</style>