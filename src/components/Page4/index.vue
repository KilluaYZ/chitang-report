<template>
  <div>
    <div class="a leadText">
      这一年 我们说过最长的一句话 <span class="value">{{ content.length }}</span
      >字
    </div>
      <div class="b userText">
          {{user}}:
      </div>
    <div class="b contentText">
      {{ content }}
    </div>
    <div class="c contentText">...</div>
    <div class="d timeText">
      {{ time }}
    </div>
  </div>
</template>

<script>
import { longMsg } from "@/data.json";
export default {
  data() {
    return {
      ...longMsg,
    };
  },
};
</script>

<style scoped>
.a {
  font-size: 5vw;
  padding-top: 2vh;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
.b {
  padding-top: 5vh;
  white-space: normal;
  text-overflow: ellipsis;
  overflow: hidden;
  line-height: 2;
  color: #ebf45f;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.d {
  text-align: right;
  padding-top: 3vh;
  font-weight: bolder;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1.5s;
  animation-fill-mode: backwards;
}

.leadText{
    color: #321e1d;
    font-size: 7vw;
}

.userText{
    color: #704d4d;
    font-size: 5vw;
    margin-bottom: -5vw;
    padding-bottom: 0;
}

.contentText{
    color: #695555;

}

.timeText{
    color: #796e6e;

}

/*.value{*/
/*    color: #c27fe8;*/
/*}*/

</style>