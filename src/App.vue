<template>
  <div id="app">
    <h1>app首页</h1>
    <button @click="showPageA = !showPageA">点击打开A页面</button>
    <p>select组件返回的数据，在首页中显示：{{ selectedData }}</p>
    <div v-if="showPageA">
      <PageA></PageA>
    </div>
  </div>
</template>

<script>
import PageA from "./views/pagea.vue";
export default {
  name: "App",
  components: {
    PageA,
  },
  provide: function () {
    return {
      selectedData: this.selectedData,
      listData: this.listData,
      setSelectedData: this.setSelectedData,
      getSelectedData: () => this.selectedData,
    };
  },
  data() {
    return {
      showPageA: false,

      // 最终选择的数据（初始化时可以赋值，组件部分需配合实现立即更新视图）
      selectedData: ["选项1"],
      // 下拉列表中所有的数据
      listData: [
        {
          value: "选项1",
          label: "黄金糕",
        },
        {
          value: "选项2",
          label: "双皮奶",
        },
        {
          value: "选项3",
          label: "蚵仔煎",
        },
        {
          value: "选项4",
          label: "龙须面",
        },
        {
          value: "选项5",
          label: "北京烤鸭",
        },
      ],
    };
  },
  methods: {
    setSelectedData(result) {
      this.selectedData = result;
    },
  },
};
</script>

<style>
#app {
  height: 100%;
  padding: 20px;
  background-color: #ebd9d9;
}
</style>
