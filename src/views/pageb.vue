<template>
  <div class="pageb-container">
    <h1>B页面</h1>
    <button @click="showSelect = !showSelect">点击打开select组件</button>
    <p>select组件返回的数据，在B页面中显示：{{ showGetSelectedData }}</p>
    <div v-if="showSelect">
      <Select
        :selected="selectedData"
        :list="listData"
        @changeData="changeData"
      ></Select>
    </div>
  </div>
</template>

<script>
import Select from "../components/Select.vue";
export default {
  name: "pageb",
  components: {
    Select,
  },
  inject: ["selectedData", "listData", "setSelectedData", "getSelectedData"],
  data() {
    return {
      showSelect: false,
      title: "title",
    };
  },
  computed: {
    showGetSelectedData() {
      return this.getSelectedData();
    },
  },
  methods: {
    changeData(result) {
      this.setSelectedData(result);
    },
  },
};
</script>

<style>
.pageb-container {
  padding: 20px;
  margin: 20px;
  border: 1px solid transparent;
  background-color: #d9ebdb;
}
</style>