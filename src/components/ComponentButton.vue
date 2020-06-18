<template>
    <div>
    <h1 v-if="format=='H1'">H1</h1>
    <h2 v-if="format=='H2'">H2</h2>
    <h3 v-if="format=='H3'">H3</h3>
    <h4 v-if="format=='H4'">H4</h4>
    <h5 v-if="format=='H5'">H5</h5>
    <h6 v-if="format=='H6'">H6</h6>
    <b v-if="format=='B'">B</b>
    <i v-if="format=='I'">I</i>
    <u v-if="format=='U'">U</u>
    </div>
</template>

<script>
export default {
    name: 'ComponentButton',
    props: {
     format: Text
    }
}
</script>