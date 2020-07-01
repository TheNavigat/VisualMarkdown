
<template>
      <modal name="properties-modal" @before-open="beforeOpen" @before-close="beforeClose">
            <input type="checkbox" id="bold-checkbox" v-model="properties.bold" />
            <label for="bold-checkbox"> bold </label>
            <input type="checkbox" id="italic-checkbox" v-model="properties.italic" />
            <label for="italic-checkbox"> italic </label>
            <input type="checkbox" id="underline-checkbox" v-model="properties.underline" />
            <label for="underline-checkbox"> underline </label>
      </modal> 
</template>

<script>
export default {
      name: "PropertiesModal",
      data(){
            return{
                  element: "",
                  properties: "",
            }
      },
      // computed: {
      //       textToShow: function(){
      //             console.log("hi", this.text)
      //             return this.text;
      //       }
      // },
      methods: {
            beforeOpen (event) {
                  this.element = event.params.element;
                  this.properties = this.element.properties;
            },
            beforeClose(){
                  this.$emit('update:properties', this.element.id, this.element)
            }
      }

}
</script>
