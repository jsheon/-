# -## **一、实验目标**

1、学习使用快速启动模板创建小程序的方法；2、学习不使用模板手动创建小程序的方法。



## 二、实验步骤

列出实验的关键步骤、代码解析、截图。

1.创建项目

![9b8177f5297d0bee97855dda4299bfd](C:\Users\ozi\AppData\Local\Temp\WeChat Files\9b8177f5297d0bee97855dda4299bfd.png)

2.手动创建小程序

先把自动生成的模板全部删掉

然后先手动添加app.js, app.json, app.wxss，app.json里面加一个大括号

再添加一个命名为pages的文件夹，在下面添加一个叫index的文件夹，再在index下面添加一个叫index的page，然后就会自动出现index.js   index.json  index.wxss  index.wxml

①我们在index.wxml里面写下这些代码

<view class='container'>
  <image src='{{src}}' mode='widthFix'></image>
  <text>{{name}}</text>
  <button open-type='getUserInfo' bindgetuserinfo='getMyInfo'\>
    点击获取头像昵称
  </button>
</view>

②我们在index.wxss里面写下这些代码

.container{

 height: 100vh;

 display: flex;

 flex-direction: column;

 align-items: center;

 justify-content: space-around;

}

image{

 width: 300rpx;

 border-radius: 50%;

}

text{

 font-size: 50rpx;

}

③我们在index.js里面写下这些代码

data: {

  src: '/images/weixin.jpg',

  name:'Hello World'

 },

 getMyInfo:function(e){

  let info=e.detail.userInfo;

  this.setData({

   src: info.avatarUrl,

   name:info.nickName

  })

 },

④我们来添加图片

先新建一个images的文件夹，然后我们将下载好的图片放在这个文件夹下面并重命名，如图所示

![f73410931c3e5167309ab6e36a63861](C:\Users\ozi\AppData\Local\Temp\WeChat Files\f73410931c3e5167309ab6e36a63861.png)

这样就手动建好了

![2d31cbdac9c051da10fe6e3e8de674a](C:\Users\ozi\AppData\Local\Temp\WeChat Files\2d31cbdac9c051da10fe6e3e8de674a.png)



## 三、程序运行结果

列出程序的最终运行结果及截图。

![8d1759c1593d5ff4ff77526b448c9f7](C:\Users\ozi\AppData\Local\Temp\WeChat Files\8d1759c1593d5ff4ff77526b448c9f7.png)

![80c44a31d381c24f7919ea7ce035d32](C:\Users\ozi\AppData\Local\Temp\WeChat Files\80c44a31d381c24f7919ea7ce035d32.png)



## 四、问题总结与体会

这次实验一开始写了代码后我的app.json的{}里面一直没有像教程所说的那样自动出现下面的代码，所以只能手动敲上

![c6576e4c2adbb7a1d8d86bcab8e9597](C:\Users\ozi\AppData\Local\Temp\WeChat Files\c6576e4c2adbb7a1d8d86bcab8e9597.png)

收获：

了解了页面文件的各个功能：

js：页面逻辑实现

json: 负责标题栏和一些状态栏

wxml: 管理页面有什么

wxss: 页面排布

还知道了这么加入一张图片还有class container怎么写

