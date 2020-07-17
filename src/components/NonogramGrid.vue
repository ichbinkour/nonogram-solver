<template>
  <div>
    <p>{{ top }} x {{ left }}</p>
    <div class="ng-container">
      <div
        v-for="t in top"
        :key="t"
        style="margin-bottom: 1em;"
        class="ng-line"
      >
        <div v-for="l in left" :key="l">
          <div v-for="ca in 5" :key="ca" style="margin-bottom: -8px;">
            <div v-for="cb in 5" :key="cb" class="ng-cell"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NonogramGrid",
  props: {
    top: {
      type: Number,
      default: 3,
    },
    left: {
      type: Number,
      default: 3,
    },
  },
};
</script>

<style lang="scss">
.ng-line {
  width: 100%;
  text-align: center; // center the content of the container
}
.ng-container {
  border: 3px solid green;
}
.ng-cell {
  border: 1px solid red;
  display: inline-block;
  width: 30px;
  height: 30px;
}
</style>
