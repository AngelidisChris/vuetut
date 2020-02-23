<template>
  <div id="app">
      <div :class="classObject">{{ value }}</div>
      <div :style="{ fontSize: value*10 + 'px' }">{{ value }}</div>

      <button type="button" @click="error = ! error">Error</button>
      <button type="button" @click="warning = ! warning">Warning</button>
      <button type="button" @click="value++">+</button>
      <button type="button" @click="value--">-</button>
  </div>
</template>

<script>
export default {
  name: 'App',

  data() {
    return {
      value: 1,
      error: false,
      warning: false,
    }
  },

  computed: {
    classObject() {
      return {
        'green-error' : this.value <= 5,
        'yellow-warning' : this.warning,
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 30px;
  padding-top: 100px;
}

  .green-error {
    background-color: greenyellow;
  }
  .yellow-warning {
    text-decoration: underline;
  }

</style>
