<template>
  <div id="app">
    <div class="container">
      <img src="@/assets/nonogram.png" alt style="width: 100px;" />

      <h1>Nonogram solver</h1>

      <div class="center">
        <b-field label="Cell(s)">
          <b-numberinput
            v-model="cellNb"
            controls-position="compact"
          ></b-numberinput>
        </b-field>
      </div>

      <nonogram-grid :cells="cellNb"></nonogram-grid>
      <b-button :disabled="!file" type="is-primary">Solve !</b-button>
    </div>

    <div>
      <div v-if="file">{{ file }}</div>
    </div>
  </div>
</template>

<script>
import NonogramGrid from "@/components/NonogramGrid.vue";

export default {
  name: "app",
  components: {
    NonogramGrid,
  },
  data() {
    return {
      file: null,
      cellNb: 2,
    };
  },
};
</script>

<style lang="scss">
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.center {
  margin: auto;
  width: 20%;
  padding: 10px;
}
</style>
