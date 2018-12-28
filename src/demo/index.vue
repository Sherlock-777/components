<template>
  <div>
    <input style="margin-bottom:20px" type="text" placeholder="请输入弹出框标题" v-model="parentTitle">
    <input style="margin-bottom:20px" type="text" placeholder="请输入弹出框内容" v-model="parentContent">
    <button style="margin-bottom:20px" @click="modalShowReturn(true)">点击这里弹出提示框</button><br>
    <button @click="alertBottom.isShow = true">点击这里弹出底部选择框</button>
    <p>你选择的值为{{demoData}}</p>
    <alert-modal v-if="isShowModal" :title="parentTitle" :content="parentContent" v-on:modalShow="modalShowReturn"></alert-modal>
    <alert-bottom :alert-bottom="alertBottom" @get-data="getData"/>
  </div>
</template>
<script>
import alertBottom from './../components/alert_bottom'
import alertModal from './../components/alert_modal'
export default {
  components: { alertModal, alertBottom },
  data () {
    return {
      isShowModal: false,
      parentTitle: '',
      parentContent: '',
      alertBottom: {
        title: '请选择',
        isShow: false,
        dataList: [
          {
            value: 1,
            desc: '选项1'
          },
          {
            value: 2,
            desc: '选项2'
          },
          {
            value: 3,
            desc: '选项3'
          },
          {
            value: 4,
            desc: '选项4'
          },
          {
            value: 5,
            desc: '选项5'
          },
          {
            value: 6,
            desc: '选项6'
          }
        ]
      },
      demoData: ''
    }
  },
  methods: {
    modalShowReturn (val) {
      this.isShowModal = val
    },
    getData (val) {
      this.demoData = val
    }
  }
}
</script>
