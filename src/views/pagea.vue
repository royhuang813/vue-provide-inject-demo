<template>
  <div class="pagea-container">
    <h1>A页面</h1>
    <button @click="showPageB = !showPageB">点击打开B页面</button>
    <p>select组件返回的数据，在A页面中显示：{{ showGetSelectedData }}</p>
    <div v-if="showPageB">
      <PageB></PageB>
    </div>
  </div>
</template>

<script>
import PageB from "../views/pageb.vue";
export default {
  name: "pagea",
  components: {
    PageB,
  },
  inject: ["getSelectedData"],
  data() {
    return {
      showPageB: false,
    };
  },
  computed: {
    showGetSelectedData() {
      return this.getSelectedData();
    },
  },
};
</script>

<style>
.pagea-container {
  padding: 20px;
  margin: 20px;
  border: 1px solid transparent;
  background-color: #ebe8d9;
}
</style>