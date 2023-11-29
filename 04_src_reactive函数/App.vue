<template>
  <h1>
    一个人的信息
    <h2>姓名:{{ person.name }}</h2>
    <h2>年龄:{{ person.age }}</h2>
    <h3>工作种类:{{ person.job.type }}</h3>
    <h3>工作薪水:{{ person.job.salary }}</h3>
    <h3>爱好:{{ person.hobby }}</h3>
    <h3>测试的数据:{{ person.a.b.c }}</h3>
    <button @click="changeInfo">修改人的信息</button>
  </h1>
</template>

<script>
import { ref, reactive } from "vue";
export default {
  name: "App",
  // 此处只是测试setup，暂时不考虑响应式的问题
  setup() {
    let person = reactive({
      name: "张三",
      age: 18,
      job: { type: "前端", salary: "30k" },
      hobby: ["抽烟", "喝酒", "烫头"],
      a: {
        b: {
          c: 666,
        },
      },
    });

    // 方法
    function changeInfo() {
      person.name = "李四";
      person.age = 48;
      person.job.type = "UI设计师";
      person.job.salary = "60k";
      person.hobby[0] = "学习";
    }

    return {
      person,
      changeInfo,
    };
  },
};
</script>

<style></style>
