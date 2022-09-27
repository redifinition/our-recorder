<template>
  <div class="home">
    <el-container>
      <el-header style="background-color: #2c3e50">Header</el-header>
      <el-container>
        <SideBar class="side-bar"></SideBar>
        <el-main>
          <DataBlock></DataBlock>
          <Calendar style="margin-top: 20px"></Calendar>
          <div style="display: flex">
            <el-image :src="require('../assets/image/dog.png')" class="small-img"></el-image>
            <h1>乔乔最近的记录～</h1>
          </div>
          <reward-card style="margin-top: 20px"></reward-card>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import DataBlock from "@/components/DataBlock";
import Calendar from "@/components/Calendar";
import SideBar from "@/components/SideBar";
import RewardCard from "@/components/RewardCard";

export default {
  name: 'HomeView',
  components: {
    RewardCard,
    SideBar,
    Calendar,
    DataBlock,
    HelloWorld
  },
  data(){
    return{
    }
  },
  methods:{}
}
</script>

<style>
  h1{
    font-weight: lighter;
    text-align: left;
    font-size: 1.2rem;
  }

  .side-bar{
    width: 300px;
  }

  .small-img{
    width: 50px;
    height: 40px;
    margin-top: 10px;
  }

  @media screen and (max-width: 600px){
    .side-bar{
      width: 60px;
    }
    h1{
      font-size: 1rem;
    }
    .small-img{
      width: 35px;
      height: 25px;
      margin-top: 10px;
    }
  }



</style>
