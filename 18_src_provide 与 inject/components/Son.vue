<template>
  <div class="son">
    <h3>我是son组件 {{ car.name }}--{{ car.price }}</h3>
  </div>
</template>

<script>
import { inject } from "vue";
export default {
  name: "Son",
  setup() {
    let car = inject("car");
    console.log(car);

    return {
      car,
    };
  },
};
</script>

<style scoped>
.son {
  background-color: yellow;
  padding: 10px;
}
</style>
