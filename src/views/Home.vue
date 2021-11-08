<template>
  <div class="home">
    <!-- <remote-js src="https://lf9-cdn-tos.bytecdntp.com/cdn/expire-1-M/three.js/72/three.min.js"></remote-js> -->
    <main>
      <div id="left">
        <div class="meter">
          <p>color</p>
          <input
            type="color"
            id="color"
            value="#ffffff"
            onclick="setColor()"
          >
        </div>
        <div class="meter">
          <p>image</p>
          <input
            type="file"
            id="texture"
            accept="image/png,image/jpeg,image/gif"
            onchange="loadTexture(this.files)"
          >
        </div>
        <div class="meter">
          <p>camera</p>
          <input
            type="range"
            id="angle"
            value="-24"
            min="-180"
            max="180"
            oninput="setCamera()"
          >
          <span id="textAngle">[0°]</span>
        </div>
        <div class="meter">
          <p>horizontal</p>
          <input
            type="range"
            id="h"
            value="0.5"
            min="0"
            max="1.0"
            step="0.1"
          >
        </div>
        <div class="meter">
          <p>vertical</p>
          <input
            type="range"
            id="v"
            value="0.3"
            min="0"
            max="1.0"
            step="0.1"
          >
        </div>
        <div class="meter">
          <p>swing</p>
          <input
            type="range"
            id="w"
            value="0.2"
            min="0"
            max="1.0"
            step="0.1"
          >
        </div>
        <div class="meter">
          <p>speed</p>
          <input
            type="range"
            id="s"
            value="0.5"
            min="0"
            max="1.0"
            step="0.1"
          >
        </div>
        <div class="meter">
          <input
            type="button"
            value="UNDO"
            onclick="initFlag()"
          >
        </div>
      </div>
      <div id="right">
        <div id="renderArea"></div>
      </div>
    </main>
  </div>
</template>

<script>

import "../assets/html.js"
export default {
  name: 'Home',
  mounted () {
    $("body").css("overflow", "hidden")

  },
  destroyed () {
    $("body").css("overflow", "")
  },
  components: {
    // eslint-disable-next-line vue/no-unused-components
    // 'remote-js': {
    //   render (createElement) {
    //     return createElement('script', { attrs: { type: 'text/javascript', src: this.src } });
    //   },

    // }
  },
}
</script>
<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  main {
    display: flex;
  }
  .meter {
    display: flex;
    width: 80%;
    margin: 15px auto;
  }
  .meter p {
    width: 120px;
    margin: 0;
  }
  .meter span {
    width: 40px;
    margin: 0 15px;
    line-height: 12px;
  }
  #left {
    width: 50%;
    display: none;
  }
  #right {
    width: 100%;
    text-align: center;
  }

  h1 {
    width: 100%;
    font-size: 48px;
    text-align: center;
  }

  input[type="range"] {
    -webkit-appearance: none;
    background-color: #cccccc;
    height: 10px;
    overflow: visible;
    width: 300px;
    position: relative;
    border-radius: 3px;
  }

  input[type="range"]::-webkit-slider-thumb {
    -webkit-appearance: none;
    background-color: #333333;
    box-shadow: 1px 1px 8px #999999;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    position: relative;
    z-index: 100;
  }

  input[type="range"]::-webkit-slider-thumb:before {
    content: "";
    position: absolute;
    top: 100%;
    left: 40%;
    width: 10%;
    height: 200px;
    display: block;
    background: red;
    z-index: -10;
    box-shadow: 0 0 10px darkred;
    opacity: 0.1;
  }

  input[type="range"]:hover::-webkit-slider-thumb:before {
    opacity: 1;
  }
}
</style>
