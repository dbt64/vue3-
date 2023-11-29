<template>
  <h1>
    一个人的信息
    <h2>姓名:{{ name }}</h2>
    <h2>年龄:{{ age }}</h2>
    <button @click="sayHello">说话</button>
  </h1>
</template>

<script>
import { h } from "vue";
export default {
  name: "App",
  // 此处只是测试setup，暂时不考虑响应式的问题
  setup(props) {
    let name = "张三";
    let age = 18;

    function sayHello() {
      alert(`我叫${name}，我${age}岁了`);
    }

    // return {
    //   name,
    //   age,
    //   sayHello,
    // };

    // 返回一个函数（渲染函数）
    return () => h("h1", "尚硅谷");
  },
};
</script>

<style></style>
