# 常规问题

## HTML标签识别
```wxml
<rich-text nodes="{{content}}"></rich-text>
```

## 指定页面不显示导航栏
```json
"navigationStyle": "custom"
```

## input实现数据双向绑定
```wxml
<input type="number" bindinput="editInput" data-name="idCode" placeholder="请输入身份证号码" value="{{idCode}}"/>

editInput (e) {
  let {name} = e.currentTarget.dataset
  let value = e.detail.value
  this.data[name] = value
  this.setData({
    name: this.data[name]
  })
},
```

## 自定义placeholder颜色和样式

```wxml
<input type="text" placeholder="请输入" placeholder-style="color:#e2e2e2;"></input>
<input type="text" placeholder="请输入" placeholder-class="placeholderStyle"></input>
```

## 图片上传组件
```wxml
<update-img class="uploadPhoto" bind:backImg="backImg"></update-img>

backImg (e) {
  let img = e.detail
}
```

## 低版本授权兼容

```wxml
wx.getSetting({
  success(res) {
    console.log(res.authSetting)
  }
})
```

## 封装下拉框

<picker-selects type="category_name" pickerList="{{educational_level}}" wx:if="{{educational_level.length}}" text="{{'政治面貌'}}" bind:traCheckedNum="checkNum"></picker-selects>



