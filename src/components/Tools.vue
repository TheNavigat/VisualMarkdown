<template>
    <div>
    <draggable
        class="dragArea list-group"
        :list="list1"
        :group="{ name: 'people', pull: 'clone', put: false }"
        @change="log"
    >
        <div
          class="list-group-item"
          v-for="element in list1"
          :key="element.format"
        >
          {{ element.format }}
        </div>
    </draggable>
    </div>
</template>

<script>
import draggable from "vuedraggable";

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
      }
    }
}
</script>

<style scoped>

</style>