<template>
  <div>
    <div class="a a-text">
<!--      今年我们一共发了-->
<!--      <span class="value"> {{ count }} </span>-->
<!--      条消息-->
        这一年里，我们真的发了很多消息~
    </div>
<!--    <div class="b">-->
<!--      其中有-->
<!--      <span class="value"> {{ imgCount }} </span>-->
<!--      是图片&nbsp; 其中有-->
<!--      <span class="value"> {{ voiceCount }} </span>-->
<!--      是语音-->
<!--    </div>-->
    <div class="b b-text">
      <div v-for="(count, word, index) in loveWord" :key="index">
        说{{ word }} <span class="value"> {{ count }} </span>次
      </div>
      <div>...</div>
    </div>
    <div class="c c-text">比起网络<br />我们更喜欢在现实表达爱意</div>
  </div>
</template>

<script>
import data from "@/data.json";
export default {
  data() {
    return {
      ...data,
    };
  },
};
</script>

<style scoped>
.a {
  font-size: 5vw;
  padding-top: 15vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: .5s;
  animation-fill-mode: backwards;
}
.b{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2s;
  animation-fill-mode: backwards;
}
.d {
  padding-top: 10vh;
  font-size: 5vw;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2.5s;
  animation-fill-mode: backwards;
}

.a-text,
.b-text,
.c-text{
    color: #321e1d;
}

.a-text{
    font-size: 9vw;
    margin-bottom: 5vw;
}

.b-text{
    font-size: 7vw;
    margin-bottom: 5vw;
}

.c-text{
    font-size: 5vw;
    margin-bottom: 5vw;
}

</style>