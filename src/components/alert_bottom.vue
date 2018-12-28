
<template>
    <div class="alert_bottom" v-if="alertBottom.isShow">
      <div class="alert_bottom_mask" @click="close(false)"></div>
      <div class="alert_bottom_body">
        <p>{{alertBottom.title}}<span @click="close(false)">取消</span></p>
        <ul>
          <li v-for="(item, index) in alertBottom.dataList" :class="{active : activeIndex == index}" :key="index" @click="sel(item.value)">{{item.desc}}</li>
        </ul>
      </div>
    </div>
</template>

<script>
/** 顶部掉落自动关闭弹窗提示 */
export default {
  props: {
    alertBottom: Object
  },
  data () {
    return {
      activeIndex: 0
    }
  },
  methods: {
    close (bool) {
      this.alertBottom.isShow = bool
    },
    sel (val) {
      this.activeIndex = val - 1
      this.$emit('get-data', val)
      this.close(false)
    }
  }
}
</script>
<style lang="scss" scoped>
.alert_bottom_mask{
  background: rgba(0,0,0,.6);
  position: fixed;
  top:0;
  left:0;
  width: 100%;
  height:100%;
  z-index: 90;
}
.alert_bottom_body{
  position: fixed;
  bottom:0;
  left: 0;
  width:100%;
  text-align: center;
  background: #fff;
  z-index: 99;
  p {
    font-size: 16px;
    color: #333333;
    font-weight: bold;
    height: 1rem;
    line-height: 1rem;
    box-shadow: 0 1px 0 0 rgba(0,0,0,0.10);
    position: relative;
    span {
      position: absolute;
      right: 10px;
      font-size: 12px;
      color: #666;
      font-weight: normal;
    }
  }
  ul {
    height: 160px;
    overflow: scroll;
    padding-left: 0;
    li{
      list-style: none;
      border-bottom: 1px solid  #E5E5E5;
      width:100%;
      background: #fff;
      line-height: 30px;
      font-size: 16px;
      font-family: PingFang-SC-Regular;
      color: #666;
      background: #fff;
      &.active{
        color: #E0B575;
      }
    }
  }
}
</style>
