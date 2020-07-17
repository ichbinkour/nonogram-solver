<template>
  <div id="app">
    <div class="container">
      <img src="@/assets/nonogram.png" alt style="width: 100px;" />
      <h1>Nonogram solver</h1>

      <div class="center">
        <b-field label="top">
          <b-numberinput
            v-model="top"
            controls-position="compact"
          ></b-numberinput>
        </b-field>
        <b-field label="left">
          <b-numberinput
            v-model="left"
            controls-position="compact"
          ></b-numberinput>
        </b-field>
      </div>

      <!-- <b-field class="file">
        <b-upload v-model="file" expanded class="uploader">
          <a class="button is-primary is-fullwidth">
            <b-icon icon="upload"></b-icon>
            <span v-if="file">{{ file.name }}</span>
            <span v-else>Click to upload</span>
          </a>
        </b-upload>
      </b-field> -->
      <nonogram-grid :top="top" :left="left"></nonogram-grid>
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
      top: 3,
      left: 3,
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
