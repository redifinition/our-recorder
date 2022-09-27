<template>
  <div id = "Calendar">
    <el-card style="border-radius: 10px;min-width: 550px">
      <el-calendar v-model="calendarDate">
        <template
            slot="dateCell"
            slot-scope="{date, data}"
            >
          {{ data.day.split('-').slice(1).join('-') }}
          <div v-for="(item,index) in scheduleData" :key="index">
            <div v-if="item.workingDay === data.day">

              <el-tag effect="dark" v-if='score.type === "plus"' v-for="(score,index) in item.scores" :key="index" style="margin-top: 2px">
                {{score.info}}<br>
                加{{score.scoreNum}}分
              </el-tag>

              <el-tag effect="dark" type='danger' v-if='score.type === "minus"' v-for="(score,index) in item.scores" :key="index" style="margin-top: 2px">
                {{score.info}}<br>
                减{{score.scoreNum}}分
              </el-tag>
            </div>
          </div>
        </template>
      </el-calendar>
    </el-card>
  </div>
</template>

<script>
import moment from "moment";

export default {
  name: "Calendar",
  data() {
    return {
      scheduleData:[
        {
          workingDay: "2022-09-07",
          scores: [
            {
              type: 'plus',
              info:'认真学习十小时',
              scoreNum: 11
            },
            {
              type: 'minus',
              info:'和女生幽会',
              scoreNum: 44
            }
          ]
        }
      ],
      calendarDate: new Date(), // 初始为当前时间
    }
  },
  methods:{

  },
  watch:{
    calendarDate(val, oldVal) {
      if (
          val &&
          moment(val).format("YYYY-MM-DD") === moment().format("YYYY-MM-DD")
      ) {
        console.log("点击了‘今天’按钮");
      } else if (
          val &&
          moment(val).toDate() < moment(oldVal).startOf("month").toDate()
      ) {
        console.log("点击了‘上个月’按钮");
      } else if (
          val &&
          moment(val).toDate() > moment(oldVal).endOf("month").toDate()
      ) {
        console.log("点击了‘下个月’按钮");
      } else {
        console.log("点击了" + moment(val).format("YYYY-MM") + "的按钮");
      }
    },
  }
}
</script>

<style>
.el-calendar-table .el-calendar-day {
  overflow: auto !important;
}

.el-tag {

  height: auto !important;
}
</style>
