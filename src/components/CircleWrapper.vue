<template>
  <div id="CircleWrapper">
    <div class="circle-wrapper" :style="{'width':width,'height':height}">
      <div :class="[CircleType[type],'circle']"></div>
      <div class="icon">
        <i :class="IconType[type]" style="width: 100%;height: 100%"></i>
      </div>
    </div>
  </div>
</template>

<script>
  const CircleType={
    success: 'success',
    error: 'error',
    warning: 'warning'
  }

  const IconType={
    success:'el-icon-success',
    error: 'el-icon-error',
    warning: 'el-icon-warning'
  }
export default {
  name: "CircleWrapper",
  props:{
    type:String,
    width: Number,
    height:Number
  },
  data(){
    return{
      CircleType,
      IconType,
    }
  }
}
</script>

<style scoped>
.circle-wrapper {
  position: relative;
  width: 50px;
  height: 50px;
  float: left;
  margin: 5px;
}

.icon {
  position: absolute;
  color: #fff;
  font-size: 25px;
  top:30px;
  left: 30px;
  transform: translate(-50%, -50%);
}

.circle {
  display: block;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  padding: 2.5px;
  background-clip: content-box;
  animation: spin 10s linear infinite;
}

.circle-wrapper:active .circle {
  animation: spin 2s linear infinite;
}

@media screen and (max-width: 1500px) {
  .circle-wrapper {
    width: 40px;
    height: 40px;
  }
  .icon {
    font-size: 20px;
    top:25px;
    left: 25px;
    transform: translate(-50%, -50%);
  }
}

@media screen and (max-width: 1200px) {
  .circle-wrapper {
    width: 30px;
    height: 30px;
  }
  .icon {
    font-size: 15px;
    top:20px;
    left: 20px;
    transform: translate(-50%, -50%);
  }
}
.success {
  background-color: #4BB543;
  border: 2.5px dashed #4BB543;
}

.error {
  background-color: #CA0B00;
  border: 2.5px dashed #CA0B00;
}

.warning {
  background-color: #F0D500;
  border: 2.5px dashed #F0D500;
}

@keyframes spin {
  100% {
    transform: rotateZ(360deg);
  }
}


</style>
