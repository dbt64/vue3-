<template>
  <div class="child">
    <h3>我是child组件</h3>
    <Son />
  </div>
</template>

<script>
import { inject } from "vue";
import Son from "@/components/Son.vue";
export default {
  name: "Child",
  setup() {
    let x = inject("car");
    
    console.log(x, "c");

    return {
      x,
    };
  },
  components: { Son },
};
</script>

<style scoped>
.child {
  background-color: skyblue;
  padding: 10px;
}
</style>
