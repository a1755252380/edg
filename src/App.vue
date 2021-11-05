<template>
  <div id="app">
    <remote-js src="https://lf9-cdn-tos.bytecdntp.com/cdn/expire-1-M/three.js/72/three.min.js"></remote-js>
    <router-view />
  </div>
</template>
<script>
export default {
  components: {
    // eslint-disable-next-line vue/no-unused-components
    'remote-js': {
      render (createElement) {
        return createElement('script', { attrs: { type: 'text/javascript', src: this.src } });
      },
      props: {
        src: { type: String, required: true },
      },
    }
  },

}
</script>
<style lang="scss">
@import url("../src/assets/html.css");
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
