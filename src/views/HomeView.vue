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
          <div style="display: flex;justify-content: space-between;flex-wrap: wrap">
            <reward-card
                v-for="record in records"
                style="margin-top: 20px"
                v-bind:record-url="record.recordUrl"
                      :record-content="record.recordContent"
                      :type="record.type"
                      :record-date="record.recordDate"
                      :record-point="record.recordPoint"></reward-card>
          </div>
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
      records:[
        {
          recordUrl: 'https://joes-bucket.oss-cn-shanghai.aliyuncs.com/img/u=3820118474,1319716523&fm=224&app=112&f=JPEG.jpeg',
          recordContent: '乔乔买了Zisga森林漫步的盲盒！dwddwwddwddwdwdwdwddwdw',
          type: 1,
          recordPoint: 7,
          recordDate: '2022-09-02 23:11',
        },
        {
          recordUrl: 'https://joes-bucket.oss-cn-shanghai.aliyuncs.com/img/u=3820118474,1319716523&fm=224&app=112&f=JPEG.jpeg',
          recordContent: '乔乔买了Zisga森林漫步的盲盒！dwddwwddwddwdwdwdwddwdw',
          type: 1,
          recordPoint: 7,
          recordDate: '2022-09-02 23：11',
        },
      ]
    }
  },
  methods:{}
}
</script>

<style scoped>
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
