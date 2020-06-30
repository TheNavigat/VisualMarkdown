<template>
  <div>
    <span v-if="format=='h1'">
      H1
    </span>
    <span v-if="format=='h2'">
      H2
    </span>
    <span v-if="format=='h3'">
      H3
    </span>
    <span v-if="format=='h4'">
      H4
    </span>
    <span v-if="format=='h5'">
      H5
    </span>
    <span v-if="format=='h6'">
      H6
    </span>
    <b v-if="format=='b'">B</b>
    <i v-if="format=='i'">I</i>
    <u v-if="format=='u'">U</u>
    <span v-if="format=='code'">code</span>
    <span v-if="format=='image'">IMG</span>
    <u v-if="format=='hyperlink'">a</u>
    <i v-if="format=='paragraph'">paragraph</i>
    <span v-if="format=='numbered-list'">1. List</span>
    <span v-if="format=='bullets-list'">*. List</span>
    <span v-if="format=='block-quote'">[Quote]</span>
    <span v-if="format=='fenced-code-block'">code block</span>
    <span v-if="format=='horizontal-rule'">====</span>
  </div>
</template>

<script>
export default {
    name: 'ComponentButton',
    props: {
     format: {
        type: String,
        default: ""
     }
    }
}
</script>