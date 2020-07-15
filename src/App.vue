<template>
  <div id="app">
    <div class="container">
      <img src="@/assets/nonogram.png" alt style="width: 100px;" />
      <h1>Nonogram solver based on images</h1>
      <b-field class="file">
        <b-upload v-model="file" expanded>
          <a class="button is-primary is-fullwidth">
            <b-icon icon="upload"></b-icon>
            <span v-if="file">{{ file.name }}</span>
            <span v-else>Click to upload</span>
          </a>
        </b-upload>
      </b-field>
      <b-button :disabled="!file" type="is-primary">Solve !</b-button>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      file: null,
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
</style>
