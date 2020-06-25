<template>
  <div>
    <button v-on:click="convertJSONToMD">Save</button>
  </div>
</template>

<script>
let MDText = "";
export default {
  name: "ActionPanel",
  components: {},
  props: {
    list2: {
      type: Array,
      default: function() {
        return [{}];
      }
    }
  },
  methods: {
    convertJSONToMD: function() {
      if (this.list2.length == 0) {
        window.alert("Empty!");
      } else {
        MDText = "";
        // LOG
        window.console.log(this.list2);
        this.list2.forEach(element => {
          MDText += this.parseMD(element) + "\n";
        });
        // LOG
        window.console.log("MD");
        // LOG
        window.console.log(MDText);
      }
    },
    parseMD: function(element) {
      // TODO if element.att is undefined
      switch (element.format) {
        /**
         * Headers
         **/
        case "h1":
          return "# " + element.text;
        case "h2":
          return "## " + element.text;

        case "h3":
          return "### " + element.text;

        case "h4":
          return "#### " + element.text;

        case "h5":
          return "##### " + element.text;

        case "h6":
          return "###### " + element.text;

        /**
         * Paragraphs
         **/
        case "b":
          return "**" + element.text + "**";

        case "i":
          return "*" + element.text + "*";

        case "u":
          return "<ins>" + element.text + "</ins>";

        case "code":
          return "`" + element.text + "`";

        case "image":
        case "hyperlink":
          return "![" + element.text + "](" + element.link + ")";

        case "paragraph":
          // TODO
          break;
        /**
         * Lists
         **/
        case "numbered-list":
          // TODO
          break;
        case "bullets-list":
          // TODO
          break;
        /**
         * Extended
         **/
        case "block-quote":
          // TODO
          break;
        case "fenced-code-block":
          return "```\n" + element.text + "\n```";
        case "horizontal-rule":
          return "\n---\n";
        default:
          return "?";
      }
    }
  }
};
</script>

<style scoped>
div {
  background: #777777;
}
</style>