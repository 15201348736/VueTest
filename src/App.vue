<!--1模板：html结构-->
<template>
  <div id="app">
    <ul>
      <!--li><a href = "/">Home</a></li>
      <li><a href = "/helloworld">Hello</a></li-->
      <li><router-link to = "/">Home</router-link></li>
      <li><router-link to = "/helloworld">Hello</router-link></li>
    </ul>
    <router-view></router-view>
  </div>
</template>

<!--2行为：处理逻辑-->
<script>

//局部注册组件
import Users from './components/Users'
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  name: 'app',
  data() {
    return {

    }
  },

}
</script>


<!--3样式：解决样式-->
<style scoped>
h1{
  color:purple;
}

</style>
