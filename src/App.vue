<template>
  <div id="app" @click.capture.stop="next">
    <!-- <template v-if="isMobile"> -->
      <template v-if="true">
      <Page1 class="delay box" v-if="step === 1" @start="next"></Page1>
      <Page2
        class="delay box"
        v-if="step === 2"
        @click.native="next"
      ></Page2>
      <Page3 class="delay box" v-if="step === 3" @next="next"></Page3>
      <Page4 class="delay box" v-if="step === 4" @next="next"></Page4>
      <Page5 class="delay box" v-if="step === 5" @next="next"></Page5>
      <Page6 class="delay box" v-if="step === 6" @next="next"></Page6>
      <Page7
        class="delay box"
        v-if="step === 7"
        @next="next"
      ></Page7>
      <Page8 class="delay box" v-if="step === 8" @next="next"></Page8>
          <Page9 class="delay box" v-if="step === 9" @next="next"></Page9>
          <Page10 class="delay box" v-if="step === 10" @next="next"></Page10>
          <Page11 class="delay box" v-if="step === 11" @next="next"></Page11>
      <!-- <div v-if="step !== 9" class="footer"></div> -->
      <div :class="handleMask"></div>
    </template>
    <template v-else> 请用手机查看 </template>
  </div>
</template>

<script>
import Page1 from "./components/Page1";
import Page2 from "./components/Page2";
import Page3 from "./components/Page3";
import Page4 from "./components/Page4";
import Page5 from "./components/Page5";
import Page6 from "./components/Page6";
import Page7 from "./components/Page7";
import Page8 from "./components/Page8";
import Page9 from "./components/Page9";
import Page10 from "./components/Page10";
import Page11 from "./components/Page11";
export default {
  name: "App",
  components: {
      Page1,
      Page2,
      Page3,
      Page4,
      Page5,
      Page6,
      Page7,
      Page8,
      Page9,
      Page10,
      Page11,
  },
  data() {
    return {
      step: 1,
      mask: true,
    };
  },
  computed: {
    handleMask() {
      return {
        mask: this.mask,
      };
    },
    isMobile() {
      return (
        /AppleWebKit.*Mobile/i.test(navigator.userAgent) ||
        /MIDP|SymbianOS|NOKIA|SAMSUNG|LG|NEC|TCL|Alcatel|BIRD|DBTEL|Dopod|PHILIPS|HAIER|LENOVO|MOT-|Nokia|SonyEricsson|SIE-|Amoi|ZTE/.test(
          navigator.userAgent
        )
      );
    },
  },
  watch: {
    step() {
      this.mask = false;
      setTimeout(() => {
        this.mask = true;
      });
    },
  },
  methods: {
    next() {
      if (this.step === 11) {
        return;
      }
      this.step++;
    },
  },
};
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
  color: white;
  overflow: hidden;
}
#app {
  /* background-image: linear-gradient(#1f9ef4, #a1e1ff); */
  background-image: url("~@/assets/images/bg_blue_pink.png");
  background-size: cover;
  height: 100vh;
  overflow: hidden;
  font-family: "Microsoft YaHei", 微软雅黑, "Microsoft JhengHei", 华文细黑,
    STHeiti, MingLiu;
  font-size: 4vw;
}
.box {
  padding: 5vw;
  padding-top: 10vw;
  overflow: hidden;
}

.delay {
  animation-name: delay-display;
  animation-duration: 3s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
@keyframes delay-display {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes slide-top {
  0% {
    opacity: 0;
    transform: translateY(10vh);
  }
  100% {
    opacity: 1;
    transform: translateY(0vh);
  }
}
.value {
  display: inline-block;
  padding: 5px;
  transform: scaleY(1.1) translateY(-5.2%);
  font-weight: bolder;
  color: #ebf45f;
}

@keyframes up-move {
    0% {
        transform: translateY(0);
        z-index: -1;
    }
    100% {
        transform: translateY(-100vh);
        z-index: 2;
    }
}
</style>

