<template>
  <div id="RewardCard">
    <el-card class="reward-card">
      <el-image :src="recordUrl" style="height: 100%;width: 40%" fit="cover">
      </el-image>
      <div style="width: 60%">
        <h1>{{recordContent}}</h1>
        <div class="text">{{type === 1 ? '+' : '-'}}{{recordPoint}}</div>
        <CircleWrapper type="success" style="float: right;margin-right: 10px;">
        </CircleWrapper>

      </div>
    </el-card>
  </div>
</template>

<script>
import CircleWrapper from "@/components/CircleWrapper";
export default {
  name: "RewardCard",
  components: {CircleWrapper},
  props:{
    recordUrl: String,
    recordContent: String,
    type: Number,
    recordPoint: Number,
    recordDate: String,
  }
}
</script>

<style scoped>
  .reward-card{
    border-radius: 20px !important;
    height: 250px;
    cursor: pointer;
    width: 550px;
  }

  .reward-card:hover{
    width: 560px;
    height: 260px;
    box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  }

  h1{
    font-weight: lighter;
    text-align: left;
    font-size: 1.2rem;
    margin-left: 10px;
    white-space:nowrap;
    text-overflow:ellipsis;
    overflow:hidden;
    display:block;
  }

  @media screen and (max-width: 1500px) {
    .reward-card{
      height: 250px;
      width: 500px;
    }

    .reward-card:hover{
      width: 510px;
    }

    h1{
      font-size: 1rem;
    }
  }

  @media screen and (max-width: 1400px) {
    .reward-card{
      height: 200px;
      width: 400px;
    }

    .reward-card:hover{
      height: 210px;
      width: 410px;
    }

    h1{
      font-size: 0.8rem;
    }
  }

  @media screen and (max-width: 1200px) {
    .reward-card{
      height: 150px;
      width: 300px;
    }

    .reward-card:hover{
      height: 160px;
      width: 310px;
    }

    h1{
      font-size: 0.6rem;
    }
  }
  /deep/.el-card__body {
    padding: 0;
    width: 100%;
    display: flex;
  }

  @import url("https://fonts.googleapis.com/css?family=Modak");


  .text {
    display: inline-block;
    font-size: 3em;
    font-family: Modak;
    padding-left: 7px;
    background-clip: text;
    -webkit-background-clip: text;
    color: transparent;
    text-shadow: 3px 3px 0px #d2d2d22e;
    background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink' width='200px' height='200px' viewBox='0 0 400 400'%3e%3cdefs%3e%3cfilter id='filter' width='400px' height='400px' filterUnits='objectBoundingBox' primitiveUnits='userSpaceOnUse' color-interpolation-filters='sRGB'%3e%3cfeFlood flood-color='%238fd3f4' flood-opacity='1' x='0' y='0' width='250px' height='250px' result='flood3'%3e%3c/feFlood%3e%3cfeFlood flood-color='%2396e6a1' flood-opacity='1' x='150px' y='150px' width='250px' height='250px' result='flood4'%3e%3c/feFlood%3e%3cfeGaussianBlur stdDeviation='50 50' x='0%25' y='0%25' width='100%25' height='100%25' in='flood3' edgeMode='none' result='blur1'%3e%3c/feGaussianBlur%3e%3cfeGaussianBlur stdDeviation='50 50' x='0%25' y='0%25' width='100%25' height='100%25' in='flood4' edgeMode='none' result='blur2'%3e%3c/feGaussianBlur%3e%3cfeBlend mode='normal' x='0%25' y='0%25' width='100%25' height='100%25' in='blur2' in2='SourceGraphic' result='blend5'%3e%3c/feBlend%3e%3cfeBlend mode='normal' x='0%25' y='0%25' width='100%25' height='100%25' in='blur1' in2='blend5' result='blend6'%3e%3c/feBlend%3e%3c/filter%3e%3c/defs%3e%3crect width='400' height='400' x='0' y='0' fill='%23d4fc79' filter='url(%23filter)'%3e%3c/rect%3e%3c/svg%3e");
  }


</style>
