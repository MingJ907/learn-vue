<template>
  <div id="app">
    <h3>这里是测试组件</h3>
    <!-- <User :age='age'/> -->
    <SlotDemo>
      <template v-slot:other="fatherOther">
        {{ fatherOther.user.firstName }}
      </template>
      <!-- v-slot:后面跟着的是插槽的name属性，而=后面的fatherOther是我们在父组件中自己定义的名称用于接收子组件插槽传递的prop -->
      <template v-slot:orderby="fatherorder">{{
        fatherorder.order.firstName
      }}</template>
    </SlotDemo>
    <SlotDemo>
      <template v-slot="{ order }">{{ order.firstName }} </template>
      <!-- 要注意的是，我们在这里使用结构插槽时，父组件内的firstName并没有替换掉子组件的lastName -->
    </SlotDemo>
    <button @click="login">登录</button>
  </div>
</template>

 <script>
import SlotDemo from "./components/SlotDemo.vue";
// import User from './components/User.vue'
// import $ from'jquery'
export default {
  name: "App",
  components: {
    SlotDemo,
    // User
  },
  methods: {
    login() {
      const username = "li";
      const password = "li000000";
      // 通过axios设置请求头发送请求
      let params=new URLSearchParams();
      params.append('username',username)
      params.append('password',password)
      this.$axios
      // ?username=${username}&password=${password}
        .post(`http://383vm21556.eicp.vip/508/login`,params)
        .then((res) => {
          console.log(res.data);
        });
        // get请求请求数据列表数组
        this.$axios.get(`http://383vm21556.eicp.vip/508/get`).then((res) =>{
          console.log(res.data);
        })


      // 通过jq发送请求
    //   $.ajax({
    //   url:'http://383vm21556.eicp.vip/shgvp/ceshi',
    //   type:"GET",
    //   data:{username:username,password:password},
    //   success(data){
    //     console.log("请求成功");
    //     console.log(data);
    //   },
    //   error(err){
    //     console.log(err);
    //     console.log("请求失败");
    //   },
    //   complete(){
    //     console.log("请求完成");
    //   }
    // })
    },
  },
  data() {
    return {};
  },
};
</script>


<style>
</style>
