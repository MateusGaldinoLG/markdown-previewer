<template>
  <div class="app">
    <textarea :value="markdownText" @input="update" name="markdown editor" rows="35" cols="30"></textarea>
    <div v-html="compiledMarkdown"></div>
  </div>
</template>

<script>
    import _ from "lodash";
    import MarkdownIt from "markdown-it";
    import emoji from "markdown-it-emoji";
    var md = new MarkdownIt({
      html: true
    }).use(emoji);

    export default {
       data(){
           return{
               markdownText: "# Hello :wave:, welcome to the markdown converter"
           }
       },
        computed: {
          compiledMarkdown: function(){
            return md.render(this.markdownText);
          }
        },
        methods: {
          update: _.debounce(function(e){
            this.markdownText = e.target.value;
          }, 300)
        } 
    }
</script>

<style lang="scss" scoped>
.app{
  margin: 0;
  height: 100%;
  font-family: "Helvetica Neue", Arial, sans-serif;
  color: #333;
}

#title{
  text-align: center;
  color: #111;
  background-color: #eee;
  padding:  5px;
  margin: 0 0 5px 0;
}

textarea, .app div{
  display: inline-block;
  width: 49%;
  height: 100%;
  vertical-align: top;
  box-sizing: border-box;
  padding: 0 20px;
}

textarea{
  border: none;
  border-right: 1px solid #ccc;
  resize: none;
  outline: none;
  background-color: #f6f6f6;
  font-size: 14px;
  font-family: "Monaco", courier, monospace;
  padding: 20px;
}

.app{
  h1{
    background-color: red;
  }
}

code{
  color: #f66;
}
</style>