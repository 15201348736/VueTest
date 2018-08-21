<!--1模板：html结构-->
<template>
  <div id="app">
    <app-header></app-header>
    <users v-bind:users = "users"></users>
    <app-footer></app-footer>
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
      users: [
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false}
      ]
    }
  },
  components:{
    "users":Users,
    "app-header":Header,
    "app-footer":Footer
  }

}
</script>


<!--3样式：解决样式-->
<style scoped>
h1{
  color:purple;
}

</style>
