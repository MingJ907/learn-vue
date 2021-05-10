<template>
  <div>
    <h3>这里是子组件</h3>
    <h2>{{namecity}}</h2>
    <h2 @click="click">{{this.age}}</h2>
  </div>
</template>

<script>
export default {
name:'User',
props:["age"],
data(){
  return{
    name:'liming',
    city:'河北'
  }
},
methods:{
  click(){
    console.log(this.name);
  }
},
computed:{
  namecity(){
    return`我叫${this.name},我来自${this.city}`
  }
},
created(){
  this.name="李明"
}
}
</script>

<style>

</style>