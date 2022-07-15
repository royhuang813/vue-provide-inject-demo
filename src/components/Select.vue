<template>
  <div class="select-container">
    <el-select v-model="value" multiple placeholder="请选择">
      <el-option
        v-for="item in list"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      >
      </el-option>
    </el-select>
  </div>
</template>

<script>
export default {
  name: "selectComponents",
  props: {
    selected: Array,
    list: Array,
  },
  data() {
    return {
      value: this.selected,
    };
  },
  watch: {
    value: {
      handler(newVal) {
        this.$emit("changeData", newVal);
      },
    },
  },
};
</script>

<style>
</style>