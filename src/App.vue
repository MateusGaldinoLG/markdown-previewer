<template>
  <Nav />
  <markdown-writer />
</template>

<script>

import MarkdownWriter from "./components/MarkdownWriter.vue";
import Nav from "./components/Nav.vue";

export default {
  name: 'App',
  components: {
    MarkdownWriter,
    Nav
  }
}
</script>

<style lang="scss">
body{
  margin: 0;
  height: 100%;
  font-family: "Helvetica Neue", Arial, sans-serif;
  color: #333;
}
</style>
