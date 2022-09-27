<template>
  <div id="SideBar">
    <el-aside style="height: 700px">
    <div style="height: 100%">
      <el-radio-group v-model="isCollapse" style="margin-bottom: 24px;margin-top: 24px" v-show="showCollapse">
        <el-radio-button :label="false">展开</el-radio-button>
        <el-radio-button :label="true">收起</el-radio-button>
      </el-radio-group>
      <el-menu default-active="1-1-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-pie-chart"></i>
            <span slot="title">我的</span>
          </template>
          <el-submenu index="1-1">
            <span slot="title">统计</span>
            <el-menu-item index="1-1-1">历史</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-menu-item index="2">
          <i class="el-icon-edit-outline"></i>
          <span slot="title">新增记录</span>
        </el-menu-item>
        <el-menu-item index="3" disabled>
          <i class="el-icon-document"></i>
          <span slot="title">导航三</span>
        </el-menu-item>
        <el-menu-item index="4">
          <i class="el-icon-setting"></i>
          <span slot="title">导航四</span>
        </el-menu-item>
      </el-menu>
      <Dog></Dog>
    </div>
  </el-aside>
  </div>
</template>

<script>
import Dog from "@/components/Dog";
export default {
  name: "SideBar",
  components: {Dog},
  data(){
    return{
      isCollapse: true,
      screenWidth: null,
      showCollapse: true,
    }
  },
  mounted () {
    this.screenWidth = document.body.clientWidth
    window.onresize = () => {
      return (() => {
        this.screenWidth = document.body.clientWidth
      })()
    }
  },
  watch:{
      screenWidth: {
        handler: function (val, oldVal) {
          if (val < 700){
            this.showCollapse = false
        } else {
          this.showCollapse = true;
        }
      },
      immediate: true
    },
  },
  methods:{
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>

<style>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 70%;
  margin-left: 10%;
  min-height: 400px;
  box-shadow: rgba(136, 165, 191, 0.48) 6px 2px 16px 0px, rgba(255, 255, 255, 0.8) -6px -2px 16px 0px;
  border-radius: 10px;
}

</style>
