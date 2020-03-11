 

# Android与H5交互文档

[TOC]

## 1、页面加载后调用

### 1、登录成功本地存储用户数据（H5传值）

方法名：receiveLoginSuc

参数说明：

| 键名         | 值说明   |
| ------------ | -------- |
| tokenKey     | token    |
| nickName     | 昵称     |
| idCard       | 身份证号 |
| ActId        | ActId    |
| headImageUrl | 头像URL  |
| phoneNum     | 手机号   |

备注：登录成功存储用户数据完成后关闭登录页面，返回登录前页面。

### 2、扫码（H5传值）

方法名：scan

备注：相应方法后调用原生扫描二维码相机，将扫描结果回传给H5.

### 3、扫码后回传扫码结果（安卓传值）

方法名：getQrCodeValue

| 键名       | 值说明   |
| ---------- | -------- |
| value      | 扫码结果 |
| androidKey | 安卓标示 |

### 4、展示toast（H5传值）

方法名：toastMsg

### 5、展示loading（H5传值）

方法名：showLoading

### 6、隐藏loading（H5传值）

方法名：hideLoading

### 7、后退，导航栏多一个关闭按钮（H5传值）

方法名：backPre

备注：H5端调用此方法，原生端需在Nav上增加一个关闭按钮，点击关闭按钮直接返回根页面，点击返回回退H5上一页

### 8、微信登录（H5传值）

方法名：wxLogin

备注：登录时调用第三方登录，相应方法内跳转微信原生登录，登录后返回微信提供的登录参数。

9、微信登录成功后给H5传值（安卓传值）

方法名：getOtherLogin

| 键名         | 值说明                                 |
| ------------ | -------------------------------------- |
| openId       | 微信、qq返回数据                       |
| accessToken  | 微信、qq返回数据                       |
| refreshToken | 微信返回数据，qq不返回该值，传空字符串 |
| unionid      | 微信返回数据，getOtherLogin            |
| type         | 微信登录填写：微信   qq登录填写：qq    |
| headImageurl | 微信、qq返回数据                       |
| nickName     | 微信、qq返回数据                       |

### 10、qq登录（H5传值）

方法名：qqLogin

备注：登录时调用第三方登录，相应方法内跳转QQ原生登录，登录后返回QQ提供的登录参数。

### 11、H5端通知原生端唤起登录界面（H5传值）

方法名：noticeLogin

备注：响应该方法后，唤起登录页面，逻辑与正常登录一样，登录完成后调用newsGetUserInfo。

### 12、新闻评论点击后H5页面获取Android登录信息

方法名：newsGetUserInfo

| 键名         | 值说明           |
| ------------ | ---------------- |
| tokenKey     | 登录返回数据     |
| idCard       | 登录返回数据     |
| nickName     | 登录返回数据     |
| ActId        | 登录返回数据     |
| phoneNum     | 登录返回数据     |
| headImageurl | 微信、qq返回数据 |

### 13、微信分享（H5传值）

方法名：wxShare

备注：响应该方法后，调用微信分享功能。

### 14、是否开启定位（H5传值）

方法名：noticeLocation

备注：响应该方法后，调用原生端是否有定位权限，如果没有，请求用户授权，如果有不请求授权。

### 15、打开摄像头（H5传值）

方法名：openCamera

备注：响应该方法后，调用原生端相机功能。

### 16、返回根页面（H5传值）

方法名：backRootView

备注：响应该方法后，关闭该webview回到原生页面。

### 17、跳转微信小程序（H5传值）

方法名：noticePushXCX

备注：响应该方法后，调用跳转微信小程序。

### 18、实名验证（H5传值）

方法名：sendVerifyCode

备注：特殊处理。

### 19、实验验证结果返回（安卓传值）

方法名：getVerifyCode

| 键名     | 值说明       |
| -------- | ------------ |
| tokenKey | 登录返回数据 |
| idCard   | 信息         |

### 20、跳转资讯详情页（H5传值）

方法名：sendNewsId

备注；H5端会返回newsID，根据newsID跳转到资讯详情页。

### 21、全部页面中调用方法（H5传值）

方法名：noticeSlide

方法名：noticeCloseSlid

方法名：closeSearch

备注：特殊处理

### 22、收藏页面中调用方法（H5传值）

方法名：jumpFavourite

方法名：deleteFavourite

备注：特殊处理

### 23、自行车页面数据请求（H5传值）

方法名：noticeBikeMap

备注：特殊处理

### 24、公积金查询（H5传值）

方法名：noticeFund

备注：特殊处理

### 25、通知跳转绿宝（H5传值）

方法名：goCarbon

备注：关闭当前页面，跳转至原生绿宝页面。

### 26、传输自行车数据（安卓传值）

方法名：getBikeMap

备注：特殊处理

### 27、点击评论通知Android准备传用户数据（H5传值）

- 方法：beforeComment

  备注：响应方法后调用newsGetUserInfo

### 28、Android传值到攻略页面（安卓传值）

- 方法名： promptMsg

| 类型             | 描述                     |
| ---------------- | ------------------------ |
| START_DATE       | 绿宝页面请求数据返回参数 |
| HISTORY_INTEGRAL | 绿宝页面请求数据返回参数 |
| androidKey       | 安卓标示                 |



## 2、页面前加载

### 1、焦点访谈页面传值（安卓传值）

方法名：interviewDetail

| 键名       | 值说明   |
| ---------- | -------- |
| talkId     | 扫码结果 |
| androidKey | 安卓标示 |

### 2、Android传值外链挂载页面（安卓传值）

方法：getWebInfo

| 键名       | 值说明                                                       |
| ---------- | ------------------------------------------------------------ |
| title      | 挂载外链title（例如：水费、电费）                            |
| androidKey | 安卓标示                                                     |
| userInfo   | 用户信息（包含tokenKey、idCard、nickName、ActId、headImageUrl、phoneNum） |

### 3、Android传值‘全部’页面信息（安卓传值）

方法：getServicesInfo

| 键名       | 值说明                                                       |
| ---------- | ------------------------------------------------------------ |
| type       | 挂载外链title（例如：水费、电费）                            |
| version    | 系统版本号                                                   |
| userInfo   | 用户信息（包含tokenKey、idCard、nickName、ActId、headImageUrl、phoneNum） |
| flag       | 首页八大按钮进入填写1、其他类推                              |
| androidKey | 安卓标示                                                     |

#### Android传搜索框的值

- 方法：getSearchVal

#### Android通知用户点击了搜索框

- 方法：beginSearch

#### Android通知用户点击了管理按钮

- 方法：manageService

#### Android通知用户点击了取消按钮

- 方法：cancelService

#### Android通知用户点击了完成按钮

- 方法：finishService

### 4、Android传值个人中心（安卓传值）

- 方法：getPersonInfo

| 键名       | 值说明                                                       |
| ---------- | ------------------------------------------------------------ |
| uuid       | 挂载外链title（例如：水费、电费）                            |
| version    | 系统版本号                                                   |
| userInfo   | 用户信息（包含tokenKey、idCard、nickName、ActId、headImageUrl、phoneNum） |
| androidKey | 安卓标示                                                     |

### 5、Android传送公告详情（安卓传值）

方法名： noticeDetail;

| 键名         | 值说明               |
| ------------ | -------------------- |
| url          | 首页请求公告返回数据 |
| news_id      | 首页请求公告返回数据 |
| detail_title | 首页请求公告返回数据 |
| source       | 首页请求公告返回数据 |
| title        | 首页请求公告返回数据 |
| createdate   | 首页请求公告返回数据 |
| content      | 首页请求公告返回数据 |
| androidKey   | 安卓标示             |

备注：此方法为首页公告专题，跳转公告详情页时使用

### 6、Android传值新闻详情页面（安卓传值）

方法：getNewsId

地址为：newly-news-subject.html 专题页面

| 键名          | 说明                                                         |
| ------------- | ------------------------------------------------------------ |
| newsId        | 专题ID                                                       |
| newsTitle     | 专题名称                                                     |
| m_flag        | 置空                                                         |
| subjectImgSrc | 专题数据图片组第一张图片                                     |
| userInfo      | 用户信息（包含tokenKey、idCard、nickName、ActId、headImageUrl、phoneNum） |
| androidKey    | 安卓标示                                                     |

其他

| 键名       | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| newsId     | 新闻ID                                                       |
| androidKey | 安卓标示                                                     |
| userInfo   | 用户信息（包含tokenKey、idCard、nickName、ActId、headImageUrl、phoneNum） |



### 7、Android传值绿宝二级页面标识（安卓传值）

- 方法名： getCarbonType

- 参数：

  | 参数       | 描述                   |
  | ---------- | ---------------------- |
  | type       | 二级页面配置(详情如下) |
  | userInfo   | 用户信息               |
  | walkNumber | 步数                   |

**绿宝二级页面type配置**

| 类型             | 描述      |
| ---------------- | --------- |
| bike             | 自行车辆  |
| bus              | 公交车辆  |
| walk             | 步行出门  |
| life             | 生活缴费  |
| medicalCare      | 在线医疗  |
| netWork          | 网上办事  |
| peopleQuery      | 便民查询  |
| OA               | 协调办公  |
| newsReading      | 新闻阅读  |
| patPat           | 随手拍拍1 |
| bloodDonation    | 爱心献血  |
| volunteerService | 志愿服务  |
| bookDonation     | 图书捐赠  |

### 8、互动模块随手拍拍、环境举报、市政报修类型及用户信息传值（安卓传值）

- 方法：getInteractInfo

| 类型       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| dataId     | 互动页面轮播图时传值、传轮播图ID，否则置空                   |
| type       | 随手拍拍“sspp”、环境举报“hjjb”、市政报修“szbx”               |
| userInfo   | 用户信息（包含tokenKey、idCard、nickName、ActId、headImageUrl、phoneNum） |
| androidKey | 安卓标示                                                     |

