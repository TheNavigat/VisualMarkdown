<template>
    <draggable
        class="dragArea list-group"
        :list="list2"
        group="people"
        @change="log"
      >
        <div
          class="list-group-item"
          v-for="element in list2"
          :key="element.format"
        >
          {{ element.format }}
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
        list2: Array
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