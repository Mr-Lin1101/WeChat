# WeChat

#### 项目介绍

小程序自定义组件-弹框

#### 安装教程

```
// 下载代码
git clone https://gitee.com/myLin/WeChat.git
```

#### 使用说明

1. 在小程序根目录下添加 components 文件，把下载的文件 dialog 粘贴到该目录下

2. 在 需要引用的 json 文件中添加以下代码

```
// 注意文件的路径
{
  "usingComponents": {
    "dialog": "/components/dialog/dialog"
  }
}
```

3. 在 wxml 文件中添加以下代码

```
<!-- 自定义-弹框 
  imgState
  success:success图片
  error:error图片 -->
  <dialog id='dialog'
    title=''
    content='您将提交该审批'
    cancelText='取消'
    confirmText='确定'
    imgState='success'
    bind:cancelEvent="_cancelEvent"
    bind:confirmEvent="_confirmEvent"/>
```

4. 在 js 文件中添加以下代码

```
  /**
    * 生命周期函数--监听页面初次渲染完成
    */
  onReady: function() {
    //获得dialog组件
    this.dialog = this.selectComponent('#dialog')
  },

  // 展示弹框
  showDialog() {
    this.dialog.showDialog()
  },

  //取消事件
  _cancelEvent() {
    console.log('你点击了取消')
    this.dialog.hideDialog()
  },
  //确认事件
  _confirmEvent() {
    console.log('你点击了确定')
    this.dialog.hideDialog()
  },
```
