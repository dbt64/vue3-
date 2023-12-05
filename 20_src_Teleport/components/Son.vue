<template>
  <div class="son">
    <h3>我是son组件</h3>
    <Diglog />
  </div>
</template>

<script>
import Diglog from "@/components/Dialog.vue";
export default {
  name: "Son",
  components: { Diglog },
};
</script>

<style scoped>
.son {
  background-color: orange;
  padding: 10px;
}
</style>
