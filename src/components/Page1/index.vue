<template>
  <!-- <div class="box">
    <div class="title">
      <div class="c">一周年</div>
      <div class="b">
        WECHAT
        <br />
        REPORT
      </div>
      <div class="c">年度聊天报告</div>
    </div>
    <div class="human">
      <div class="boy">
        <img class="a" src="@/assets/images/cmw.png" />
        <img class="b" src="@/assets/images/cloud1.png" />
      </div>
      <div class="girl">
        <img class="a dte" src="@/assets/images/dte.png" />
        <img class="b" src="@/assets/images/cloud2.png" />
      </div>
    </div>
    <div class="star">
      <div class="circle" @click="$emit('start')">
        <div class="left" @click="$emit('start')">→</div>
      </div>
      <div class="label" @click="$emit('start')">点击开启</div>
    </div>
  </div> -->

  <div class="flex-container" >
    <div id="headerRow" class="flex-container">
      <div>
<!--        <div class="headerRowText">你是我触摸不到的风</div>-->
          <img class="p" src="@/assets/images/sologen.png" />
      </div>
    </div>

    <div id="footRow">
        <div><span class="footRowText">一周年聊天报告~</span></div>
      <div class="star">
        <div class="circle" @click="$emit('start')">
          <div class="left" @click="$emit('start')">→</div>
        </div>
<!--        <div class="label" @click="$emit('start')">点击开启</div>-->
      </div>


    </div>

  </div>
</template>

<script>
export default {};
</script>

<style scoped>
*{
    margin:0;
    padding:0;
}

#footRow {
    display: flex;
    flex-wrap: nowrap;
    flex-direction: row;
    align-items: center;
    align-self: end;
}

#headerRow {
    height: 60%;
    width: 100%;
    padding: 120px;
    margin-bottom: 40vw;
}

.flex-container{
    display: flex;
    flex-direction: column;
    align-items: center;
}

.flex-direction-row{
  flex-direction: row;
}

.flex-direction-column{
  flex-direction: column;
}

.flex-wrap-no{
    flex-wrap: nowrap;
}

.flex-justify-content-end{
    justify-content: end;
}

.flex-wrap-yes{
    flex-wrap: wrap;
}

/*@font-face{*/
/*    font-family: myFont1;*/
/*    src: url("@/assets/font/myFont1.ttf") format("truetype);*/
/*    font-weight: 100;*/
/*    font-style: normal;*/
/*}*/

.headerRowText {
    font-size: x-large;
    color: rgba(50, 31, 28, 0.99);
}

.footRowText {

  font-size: 15vw;
  color: #321e1d;
}

.title {
  color: white;
  line-height: 1;
  display: grid;
  grid-template-columns: max-content 1fr;
}

.title .a {
  font-size: 25vw;
}

.title .b {
  /*padding-top: 1em;*/
  font-size: 5vw;
}

.title .c {
  font-size: 10vw;
}

.human .boy {
  position: relative;
  top: -10vh;
  animation: up-down 2s ease-in-out infinite both;
}

.human .girl {
  position: relative;
  top: -20vh;
  left: 30vw;
  animation: up-down 2s ease-in-out infinite both;
}

@keyframes up-down {
  0% {
    transform: translateY(1vh);
  }

  50% {
    transform: translateY(0vh);
  }

  100% {
    transform: translateY(1vh);
  }
}

.human .boy .a {
  width: 27vw;
  position: relative;
  left: 10vw;
  top: 15vh;
  z-index: 2;
}

.human .boy .b {
  width: 50vw;
  position: relative;
  left: -30vw;
  top: 20vh;
}

.human .girl .a {
  width: 57vw;
  position: relative;
  left: 5vw;
  top: 15vh;
  z-index: 2;
}

.human .girl .b {
  width: 50vw;
  position: relative;
  left: 5vw;
  top: -5vh;
}

.dte {
  width: auto;
  height: 40vw;
}

.star {
  /*position: absolute;*/
  /*bottom: 10vh;*/
  /*left: calc(50vw - 15vw);*/
    margin-left: 8vw;
    margin-right: 3vw;
}

.star .circle {
  width: 25vw;
  height: 25vw;
  border-radius: 100%;
  background-color: rgba(253, 49, 1, 0.99);
  text-align: center;
  font-size: 22vw;
  color: white;
  animation: hvr-ripple-out 2s ease-in-out infinite alternate both;
}

@keyframes hvr-ripple-out {
  100% {
    transform: scale(1.05);
  }
}

.star .label {
  font-size: 5vw;
  text-align: center;
  font-weight: lighter;
}

.p {
    position: absolute;
    width: 60vw;
    left: 20%;
    top: 15vh;
    z-index: 2;
}

</style>