# 弹出框组件
***
## 本地运行
***
npm run dev
## 插件应用
***
### 局部导入组件
***
```
import alertModal from 'alert_modal'
export default {
  name: 'HelloWorld',
  components: {
    alertModal
  }
}
```
### 全局导入组件
***
`import alertModal from 'alert_modal'`
`Vue.component('alert-modal',alertModal)`
#### 使用组件
***
`<alert-modal v-if="isShowModal" :title="parentTitle" :content="parentContent" v-on:modalShow="modalShowReturn"></alert-modal>`
#### 组件参数
***
名称|类型|默认值|说明
:--:|:--:|:--:|:--:
isShowModal|bool|false|弹框是否默认显示
title|string|-|弹框标题
content|string|-|弹框内容
modalShow|bool|false|弹框开启关闭
***
# 底部选择框组件
***
## 本地运行
***
npm run dev
## 插件应用
***
### 局部导入组件
***
```
import alertBottom from 'alert_bottom'
export default {
  name: 'HelloWorld',
  components: {
    alertBottom
  }
}
```
### 全局导入组件
***
`import alertBottom from 'alert_bottom'`
`Vue.component('alert-bottom',alertBottom)`
#### 使用组件
***
`<alert-bottom :alert-bottom="alertBottom" @get-data="getData"/>`
#### 组件参数
***
名称|类型|默认值|说明
:--:|:--:|:--:|:--:
alert-bottom|obj|-|弹框数据对象
getData|obj|-|返回的选择数据
