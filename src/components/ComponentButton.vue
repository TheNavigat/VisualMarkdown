<template>
    <div>
    <h1 v-if="format=='h1'">H1</h1>
    <h2 v-if="format=='h2'">H2</h2>
    <h3 v-if="format=='h3'">H3</h3>
    <h4 v-if="format=='h4'">H4</h4>
    <h5 v-if="format=='h5'">H5</h5>
    <h6 v-if="format=='h6'">H6</h6>
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
     format: String
    }
}
</script>