<template>
  <button @click="isShowDemo = !isShowDemo">切换隐藏/显示</button>
  <Demo v-if="isShowDemo" />
  <Test />
</template>

<script>
import { ref } from "vue";
import Test from "./components/Test.vue";
import Demo from "./components/Demo";
export default {
  name: "App",
  components: { Demo, Test },
  setup(props) {
    let isShowDemo = ref(true);

    return {
      isShowDemo,
    };
  },
};
</script>

<style></style>
