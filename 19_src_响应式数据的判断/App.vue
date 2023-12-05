<template>
  <h3>我是app组件</h3>
</template>

<script>
import {
  reactive,
  toRefs,
  ref,
  readonly,
  isRef,
  isReactive,
  isReadonly,
  isProxy,
} from "vue";
export default {
  name: "App",
  setup() {
    const car = reactive({
      name: "奔驰",
      price: "40w",
    });

    let sum = ref(0);
    const car2 = readonly(car);

    console.log(isRef(sum));
    console.log(isReactive(car));
    console.log(isReadonly(car2));
    console.log(isProxy(sum));

    return { ...toRefs(car) };
  },
};
</script>

<style scoped></style>
