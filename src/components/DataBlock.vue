<template>
  <div id = "DataBlock">
    <el-card style="border-radius: 10px;width: 100%;min-width: 200px">
      <h1 style="font-weight: lighter;text-align: left;margin-block-start: 0">在一起已经{{togetherDayNum}}天</h1>
      <div style="display: flex;align-items:center;width: 100%;height: 100%">
        <el-avatar class = "user-avatar" :src="avatar"></el-avatar>
          <h1 class = 'score'>
            {{loveScore}}/100
          </h1>
          <el-tooltip class="item" effect="dark" :content="toolTipContent" placement="left-start" style="margin-bottom: 10%">
            <i class="el-icon-question"></i>
          </el-tooltip>
        <div style="margin-left: auto;width: 30%">
          <el-button type="primary" icon="el-icon-edit" class="new-edit-button">
            新增记录
          </el-button>
          <el-button type="primary" icon="el-icon-edit" class="new-edit-button-small">
          </el-button>
          <h1 class="last-record-font">2022-09-16,买了盲盒,加5分</h1>
        </div>
      </div>
    </el-card>
  </div>
</template>

<script>
import * as moment from 'moment';

export default {
  name: "DataBlock",
  data(){
    return{
      avatar: "",
      loveScore: '',
      toolTipContent: '该分数是截止目前小狗获得的分数哦',
      togetherDayNum: 10
    }
  },
  created() {
    this.avatar = "https://joes-bucket.oss-cn-shanghai.aliyuncs.com/img/IMG_4288.jpg"
    this.loveScore = 87
    const startDate = moment('2022-08-14','YYYY-MM-DD')
    const nowDate = moment();
    this.togetherDayNum = nowDate.diff(startDate,'day')
  }
}
</script>

<style scoped>
  .user-avatar{
    width: 150px;
    height: 150px;
    box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  }

  .score{
    font-size: 3em;
    font-weight: lighter;
    margin-left:20px;
  }

  .new-edit-button{
    display: block;
  }
  .new-edit-button-small{
    display: none;
  }

  .last-record-font{
    font-weight: lighter;
  }

  .is-selected {
    color: #008080FF;
  }

  @media screen and (max-width: 1000px) {
    .user-avatar{
      width: 100px;
      height: 100px;
      box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
    .score{
      font-size: 2em;
    }
  }

  @media screen and (max-width: 700px) {
    .user-avatar{
      width: 80px;
      height: 80px;
      box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
    .score{
      font-size: 1em;
    }

    .last-record-font{
      font-size: 1em;
      text-align: center;
    }
  }

  @media screen and (max-width: 600px) {
    .user-avatar{
      width: 60px;
      height: 60px;
      box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
    .score{
      font-size: 1em;
    }
    .new-edit-button{
      display: none;
    }
    .new-edit-button-small{
      display: block;
    }
    .last-record-font{
      font-size: 0.5em;
    }
  }
</style>
