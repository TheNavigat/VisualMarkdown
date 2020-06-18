<template>
    <div>
    <draggable
        class="dragArea list-group"
        :list="list1"
        :group="{ name: 'markdown', pull: 'clone', put: false }"
        @change="log"
        :clone="cloneMethod"
    >
        <span
          class="list-group-item"
          v-for="element in list1"
          :key="element.id"
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
let idGlobal = 5;

export default {
    name: 'Tools',
    components:{
        draggable,
        ComponentButton
    },
    props:{
      list1: Array
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