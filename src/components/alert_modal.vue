
<template lang="html">
  <div class="customerservice">
    <b class="icon" @click="colseAlert(false)">x</b>
    <div class="customerservice-box">
      <div class="explain">
        <h1>{{title}}</h1>
        <hr>
        <div class="iscroll">
        <p v-html="content"></p>
        <div class="bottom">
        </div>
        </div>
      </div>
    </div>
    <div class="fixed-bg" @click="colseAlert(false)"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  props: ['title', 'content'],
  methods: {
    // 关闭客服弹窗
    colseAlert (a) {
      this.$emit('modalShow', a)
    }
  }
}
</script>
<style lang="scss" scoped>
.customerservice{
  position: fixed;
  width: 100%;
  top: 25%;
  z-index: 999;
  left: 0;
  right: 0;
  .icon {
    position: absolute;
    right: 2rem;
    top: .2rem;
  }
  .fixed-bg{
    content: '';
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0,0,0,.6);
    z-index: -1;
  }
  .iscroll {
    overflow: scroll;
    height: 7.4rem;
  }
  .customerservice-box {
    z-index: 2;
    background: #fff;
    width: 80%;
    margin: 0 auto;
    border-radius: .2rem;
    padding: .4rem;
    .explain {
      hr {
        opacity: 0.1;
        background: #000000;
        margin: .3rem auto;
      }
      h1 {
        text-align: center;
        font-family: PingFang-SC-Regular;
        font-size: .28rem;
        color: #666;
      }
      h2 {
        font-family: PingFang-SC-Regular;
        font-size: .24rem;
        color: #666;
      }
      p {
        font-family: PingFangSC-Regular;
        font-size: .22rem;
        color: #666666;
        line-height: .4rem;
      }
      .bottom {
        margin-top: .07rem;
        text-align: right;
      }
    }
  }
}
</style>
