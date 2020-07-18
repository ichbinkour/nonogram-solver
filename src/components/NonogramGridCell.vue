<template>
  <div class="ng-container-cell">
    <div v-for="line in 5" :key="line" class="ng-line">
      <input v-if="side" type="text" />
      <div v-for="row in 5" :key="row" class="ng-cell"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NonogramGridCell",
  props: {
    side: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
.ng-cell {
  border: 1px solid #344861;
  display: inline-block;
  width: 30px;
  height: 30px;
}
.ng-line {
  display: flex;
  width: 100%;
}
.ng-container-cell {
  border: 2px solid #344861;
}
</style>
