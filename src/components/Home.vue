<!--1模板：html结构-->
<template>
  <div id="home">
    <app-header v-on:titleChanged="updateTitle($event)" v-bind:title="title"></app-header>
    <users v-bind:users="users"></users>
    <users v-bind:users="users"></users>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<!--2行为：处理逻辑-->
<script>

//局部注册组件
import Users from './Users'
import Header from './Header'
import Footer from './Footer'

export default {
  name: 'home',
  data() {
    return {
      users: [
        /*{name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false},
        {name:"Henry",position:"Web开发",show:false}*/
      ],
      title: " 传递的是一个值，（number  string  boolean）"
    }
  },
  methods: {
    updateTitle(title) {
      this.title = title;
    }
  },
  components: {
    "users": Users,
    "app-header": Header,
    "app-footer": Footer
  },
  created() {
   /* this.$http.get("http://jsonplaceholder.typicode.com/users")
        .then((data) => {
        console.log(data);
        this.users = data.body;*/
        //以上为一个跨域的请求，不能直接去访问别的后台，可以用下面JSONP解决这个问题

    this.$http.jsonp("http://jsonplaceholder.typicode.com/users",{},{
       headers: {},
      emulateJSON: true }).then((data) => {
        //console.log(data);
        this.users = data.body;
    })
  }

}
</script>


<!--3样式：解决样式-->
<style scoped>
h1 {
  color: purple;
}
</style>
