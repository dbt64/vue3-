<template>
  <h2>姓名：{{ name }}</h2>
  <h2>年龄：{{ age }}</h2>
  <h2>薪资: {{ job.j1.salary }}k</h2>
  <button @click="name += '~'">修改姓名</button>
  <button @click="age++">增长年龄</button>
  <button @click="job.j1.salary++">增长薪资</button>
</template>

<script>
import { reactive, toRef, toRefs } from "vue";
export default {
  name: "Demo",
  setup() {
    // 数据
    let person = reactive({
      name: "zs",
      age: 18,
      job: {
        j1: {
          salary: 20,
        },
      },
    });

    // const name2 = toRef(person, "name");
    // console.log(name2);

    // 返回一个对象（常用）
    return {
      ...toRefs(person),
    };
  },
};
</script>

<style></style>
