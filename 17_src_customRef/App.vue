<template>
  <input type="text" v-model="keyword" />
  <h3>{{ keyword }}</h3>
</template>

<script>
import { ref, customRef } from "vue";
export default {
  name: "App",
  setup() {
    // 自定义的ref——名为 MyRef
    function MyRef(data, delay) {
      let timer;
      return customRef((track, trigger) => {
        return {
          get() {
            console.log("有人从MyRef读取数据了");
            track(); // 通知vue追踪value的变化（提前和get商量一下，让他认为这个value是有用的)
            return data;
          },
          set(value) {
            console.log("有人把MyRef修改了");
            clearTimeout(timer);
            timer = setTimeout(() => {
              data = value;
              trigger(); // 通知vue去重新解析模板
            }, delay);
          },
        };
      });
    }
    // let keyword = ref("hello"); // 使用vue提供的ref
    let keyword = MyRef("hello", 500); // 使用程序员提供的ref

    return {
      keyword,
    };
  },
};
</script>

<style></style>
