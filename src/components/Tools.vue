<template>
    <div>
    <draggable
        class="dragArea list-group"
        :list="list1"
        :group="{ name: 'markdown', pull: 'clone', put: false }"
        @change="log"
        :clone="cloneMethod"
    >
        <div
          class="list-group-item"
          v-for="element in list1"
          :key="element.id"
        >
          <button>
          {{ element.format }}
          </button>
        </div>
    </draggable>
    </div>
</template>

<script>
import draggable from "vuedraggable";
let idGlobal = 5;

export default {
    name: 'Tools',
    components:{
        draggable
    },
    props:{
      list1: Array
    },
    methods: {
      log: function(evt) {
        window.console.log(evt);
      },
      cloneMethod({id, format}){
        console.log(id)
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