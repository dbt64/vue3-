<template>
  <h4>当前的x是：{{ x.y }}</h4>
  <button @click="x.y++">点给我x加以</button>
  <hr />
  <h2>{{ person }}</h2>
  <h2>姓名：{{ name }}</h2>
  <h2>年龄：{{ age }}</h2>
  <h2>薪资: {{ job.j1.salary }}k</h2>
  <button @click="name += '~'">修改姓名</button>
  <button @click="age++">增长年龄</button>
  <button @click="job.j1.salary++">增长薪资</button>
</template>

<script>
import { reactive, toRef, toRefs, shallowReactive, shallowRef, ref } from "vue";
export default {
  name: "Demo",
  setup() {
    // 数据
    // let person = shallowReactive({ // 只考虑第一层的响应式
    let person = reactive({
      name: "zs",
      age: 18,
      job: {
        j1: {
          salary: 20,
        },
      },
    });
    let x = shallowRef({
      y: 0,
    });

    // 返回一个对象（常用）
    return {
      person,
      ...toRefs(person),
      x,
    };
  },
};
</script>

<style></style>
