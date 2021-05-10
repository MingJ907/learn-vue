<template>
  <div>
    <h2>这里是拥有插槽的子组件</h2>
    <slot name='other' :user='user'>{{user.lastName}}</slot>
    <slot name='orderby' :order='order'>{{ order.lastName }}</slot>
  </div>
</template>

<script>
export default {
  name: "SlotDemo",
  data() {
    return {
      user:{ firstName: "谷小桐", lastName: "ming" },
      order:{
        lastName: "li",
        firstName: "ming",
      },
    };
  },
};
</script>

<style>
</style>