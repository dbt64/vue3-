<template>
  <h1>
    一个人的信息
    <h2>姓名:{{ name }}</h2>
    <h2>年龄:{{ age }}</h2>
    <h3>工作种类:{{ job.type }}</h3>
    <h3>工作薪水:{{ job.salary }}</h3>
    <button @click="changeInfo">修改人的信息</button>
  </h1>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  // 此处只是测试setup，暂时不考虑响应式的问题
  setup(props) {
    let name = ref("张三");
    let age = ref(18);
    let job = ref({
      type: "前端",
      salary: "30k",
    });

    // 方法
    function changeInfo() {
      name.value = "李四";
      age.value = 48;
      job.value.type = "UI设计师";
      job.value.salary = "60k";
    }

    return {
      name,
      age,
      job,
      changeInfo,
    };
  },
};
</script>

<style></style>
