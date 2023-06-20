<template>
  <div>
    <div class="a leadText">
        {{bestMoments[2].time}}
    </div>

<!--      <el-carousel indicator-position="outside">-->
<!--          <el-carousel-item v-for="moment in bestMoments" :key="moment">-->
<!--              -->
<!--          </el-carousel-item>-->
<!--      </el-carousel>-->

      <div class="chatBlock">
          <div class="b" v-for="item in bestMoments[2].chats" :key="item">
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
  </div>
</template>

<script>
import { bestMoments } from "@/data.json";
export default {
  data() {
    return {
      bestMoments,
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
  /*white-space: normal;*/
  /*text-overflow: ellipsis;*/
  /*overflow: hidden;*/
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
    height: 60vh;
    display: flex;
    flex-direction: column;
    margin: 5vw;
    /*border: 1px solid white;*/
    overflow-y: scroll;
    margin-left: 2vw;
    margin-right: 2vw;
    margin-bottom: 5vw;
}

.singleChatItem{
    display: flex;
    flex-direction: column;
}

.chatItemRight .singleChatItem{
    align-items: end;
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

.el-carousel__item h3 {
    color: #475669;
    font-size: 18px;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
}

.el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
}

</style>