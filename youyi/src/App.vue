<template>
  <div id="app">
    <Home></Home>
  </div>
</template>

<script>
import Home from './views/home/home.vue'
export default {
  name: 'app',
  components: {
    Home
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
* {
  margin: 0;
  padding: 0;
}
#app {
  width: 100%;
}
html,
body {
  width: 100%;
  height: 100%;
  background-color: #f9f9f9;
}
.container {
  text-align: center;
  margin: 0 auto;
  width: 1200px;
  /* overflow: hidden; */
}
.clearfix:after {
  content: ''; /*设置内容为空*/
  height: 0; /*高度为0*/
  line-height: 0; /*行高为0*/
  display: block; /*将文本转为块级元素*/
  visibility: hidden; /*将元素隐藏*/
  clear: both; /*清除浮动*/
}
.fd{
  float: left;
}
</style>
