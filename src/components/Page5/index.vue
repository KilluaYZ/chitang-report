<template>
  <div>
    <div class="a leadText">
      这一年 我们说过最晚的一句话
      <br />
      在凌晨
      <span class="value">
        {{ hour }}
      </span>
      点
    </div>
<!--    <div class="b">-->
<!--      <span style="font-size: 3.6vw"> {{ user }}: </span>-->
<!--      {{ content }}-->
<!--    </div>-->

      <div class="chatBlock">
          <div class="b" v-for="item in chat" :key="item.id">
              <div v-if="item.user === 'dte'" class="chatItemRight">
                  <div class="singleChatItem">
                      <div class="userText"><span>{{item.user}}</span></div>
                      <div class="contentText"><span>{{item.content}}</span></div>
                  </div>
              </div>
              <div v-else class="chatItemLeft">
                  <div class="singleChatItem">
                      <div class="userText"><span>{{item.user}}</span></div>
                      <div class="contentText"><span>{{item.content}}</span></div>
                  </div>
              </div>
          </div>
      </div>
    <div class="c">...</div>
    <div class="d timeText">
      {{ time }}
    </div>

    <div class="e" style="padding-top: 5vh; font-size: 5vw">那天在做什么还能记起来吗</div>
  </div>
</template>

<script>
import { latestMsg } from "@/data.json";
export default {
  data() {
    return {
      ...latestMsg,
    };
  },
};
</script>

<style scoped>
.a {
  font-size: 5vw;
  padding-top: 1vw;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 0.5s;
  animation-fill-mode: backwards;
}
.b {
  white-space: normal;
  text-overflow: ellipsis;
  overflow: hidden;
  line-height: 2;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1s;
  animation-fill-mode: backwards;
}
.c {
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 1.5s;
  animation-fill-mode: backwards;
}
.d {
  text-align: right;
  padding-top: 3vh;
  font-weight: bolder;
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2s;
  animation-fill-mode: backwards;
}
.e{
  animation-name: slide-top;
  animation-duration: 1s;
  animation-delay: 2.5s;
  animation-fill-mode: backwards;
}

.chatItemLeft{
    display: flex;
    flex-direction: row;
    justify-content: start;
    margin-top: -2vw;
}

.chatItemRight{
    display: flex;
    flex-direction: row;
    justify-content: end;
}

.chatBlock{
    display: flex;
    flex-direction: column;
    margin: 5vw;
    /*border: 1px solid white;*/

}

.singleChatItem{
    display: flex;
    flex-direction: column;
}

/*.chatItemRight .userText{*/
/*    margin-left: -5vw;*/
/*}*/

/*.chatItemLeft .contentText{*/
/*  margin-left: 5vw;*/
/*}*/

.userText{
    margin-bottom: -2vw;
    color: #7a6a6a;
}

.contentText{
    color: #817373;
    border: 1px solid white;
    border-radius: 10px;
    background-color: white;
    padding-left: 2vw;
    padding-right: 2vw;
}

.timeText{
    color: #796e6e;
}

.leadText{
    color: #321e1d;
}

</style>