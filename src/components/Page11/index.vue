<template>
  <div class="v">
    <div class="a">
      <div class="b">#蛙历元年~</div>
      <div class="c">一周年聊天报告</div>
      <div class="d">关键词</div>
      <div class="e">喜欢</div>
      <div class="f"></div>
      <div class="d">爱意词</div>
      <div class="e">{{ b }}</div>
      <div class="f"></div>
      <div class="d">话痨月</div>
      <div class="e" style="font-size: 10vw">每一月</div>
      <div class="f"></div>
      <div class="h">
         <img class="p" src="@/assets/images/dtehecmw.png" />
        <img class="y" src="@/assets/images/cloud2.png" />
      </div>
      <div class="j">新的一年</div>
      <div class="i">我们来咯~</div>
    </div>
  </div>
</template>

<script>
import data from "@/data.json";
export default {
  data() {
    const { loveWord, mostWord, monthGroup } = data;
    let max = monthGroup[0];
    for (let i of monthGroup) {
      if (i[1] > max[1]) {
        max = i;
      }
    }
    let lc = {
      w: "",
      c: 0,
    };
    Object.keys(loveWord).forEach((key) => {
      const count = loveWord[key];
      if (count > lc.c) {
        lc = {
          w: key,
          c: count,
        };
      }
    });

    let mc = {
      w: "",
      c: 0,
    };

    Object.keys(mostWord).forEach((key) => {
      const count = mostWord[key];
      if (count > mc.c) {
        mc = {
          w: key,
          c: count,
        };
      }
    });
    return {
      a: mc.w,
      b: lc.w,
      c: max[0],
    };
  },
};
</script>

<style scoped>
.v {
  background-image: linear-gradient(#f89d92, #fac9bf);
  height: 100%;
  color: #73e373;
}
.a {
  margin-top: 10vh;
  height: 60vh;
  border: 5px #73e373 solid;
  background: #fef9f9;
  padding: 5vw;
}
.b {
  font-size: 13vw;
  padding-bottom: unset;
}
.c {
  font-size: 5vw;
  font-weight: 700;
  padding-bottom: 5vh;
}
.d {
  color: black;
  font-weight: bold;
}
.e {
  color: black;
  /* font-weight: bold; */
  font-size: 12vw;
}
.f {
  height: 1px;
  background: #73e373;
  width: 30vw;
  margin-top: 2vh;
  margin-bottom: 2vh;
}
.p {
  position: absolute;
  width: 30vw;
  left: 57vw;
  top: 55vh;
  z-index: 2;
}
.y {
  position: absolute;
  width: 60vw;
  left: 50vw;
  top: 60vh;
}
.i,
.j {
  position: absolute;
  color: #3c4739;
}
.j {
  font-size: 10vw;
  top: 25vh;
  left: 50vw;
    margin-top: 10vw;
}
.i {
  font-size: 10vw;
  top: 32vh;
  left: 53vw;
    margin-top: 15vw;
}
</style>