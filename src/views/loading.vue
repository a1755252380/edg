<template>
  <div class="abody">
    <div class="divimg">
      <div class="img imgshow"></div>
    </div>
    <HomeVue></HomeVue>
  </div>
</template>
<script>
import HomeVue from './Home.vue';

export default {
  mounted () {
    let width2 = document.documentElement.clientWidth

    if (width2 >= 1440) {
      $(".img").css("height", "100%")
    } else if (width2 < 1440 && width2 >= 768) {
      $(".img").css("height", "100%")
      $(".imgshow").css("backgroundSize", "140%")
    } else if (width2 < 768) {
      $(".imgshow").css("backgroundSize", "320%")
      $(".imgshow").css("backgroundPositionX", "4%")
    }
    setTimeout(() => {
      $(".imgshow").removeClass("imgshow");
      $(".img").css("display", "none")
      $(".divimg").css("display", "none")
    }, 5000);
  },
  components: {
    HomeVue
  }
}
</script>
<style lang="scss" scoped>
.abody {
  display: flex;
  height: 100%;
  width: 100%;
  align-items: center;
  justify-content: center;
  padding: 0;
  margin: 0;
}
.divimg {
  position: fixed;
  background: #000;
  height: 100%;
  width: 100%;
  -webkit-animation: rotate22 5s infinite linear;
  animation: rotate22 5s infinite linear;
}
@keyframes rotate22 {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
  100% {
    opacity: 0;
  }
}
@-webkit-keyframes rotate22 {
  0% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
  100% {
    opacity: 0;
  }
}
.img {
  width: 100%;
  height: 100%;
  background: url("../assets/a.jpg") no-repeat;
  background-size: 100%;

  left: 0;
  top: 0;
}
.imgshow {
  -webkit-animation: rotate22 5s infinite linear;
  animation: rotate22 5s infinite linear;
}
</style>