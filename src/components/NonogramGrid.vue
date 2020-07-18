<template>
  <div>
    <div class="ng-container">
      <div v-for="row in cells" :key="row" class="ng-container-line">
        <div v-for="col in cells" :key="col + '-' + row">
          <nonogram-grid-cell></nonogram-grid-cell>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NonogramGridCell from "@/components/NonogramGridCell.vue";

export default {
  name: "NonogramGrid",
  components: {
    NonogramGridCell,
  },
  props: {
    cells: {
      type: Number,
      default: 1,
    },
  },
};
</script>

<style lang="scss">
.ng-container {
  padding-bottom: 1em;
  width: 100%;
  margin: auto;
}
.ng-cell {
  border: 1px solid red;
  display: inline-block;
  width: 30px;
  height: 30px;
}
.ng-container-line {
  display: flex;
}
</style>
