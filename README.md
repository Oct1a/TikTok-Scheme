# TikTok-Scheme
抖音、抖音极速版、tiktok 快手 等主流APP的Scheme schemas获取，**将持续更新**。。。

### 应用后期变更scheme导致出现错误,欢迎PR,一起维护，如对您有帮助，请给个Star⭐

>  以下各种Scheme在PC或其它设备上都是无效的，所以只有Android设备能识别这类连接并进行启动，ios内部schema是aweme开头，所提替换链接上的schema为 aweme 开头




## 抖音Schema
> 网址仅抖音内部人员查看
> gd_label是唤起应用时，通知客户端记录打点的字段
> gd_label参数： https://wiki.bytedance.net/pages/viewpage.action?pageId=179404954
> gd_label的值有哪些： https://docs.google.com/spreadsheets/d/1EWzh4gIbE861d9Rbk-M7QNYCPnltkNt9r2ETVSV2wf4/edit#gid=2126697475
>
> 有一些参数是可以忽略的，具体可以自测一下，之前用过忘记记录了....

| Schema | 描述 |
| -------------------- | ------------------- |
| snssdk1128://feed?refer=web&gd_label={{gd_label}}   | 首页feed     |
| snssdk1128://aweme/detail/{{id}}?refer=web&gd_label={{gd_label}}&appParam={{appParam}}&needlaunchlog=1'   | 作品详情页     |
| snssdk1128://user/profile/{{uid}}?refer=web&gd_label={{gd_label}}&type={{type}}&needlaunchlog=1   | 用户主页 |
| snssdk1128://challenge/detail/{{id}}?refer=web&is_commerce=0   | 挑战详情     |
| snssdk1128://music/detail/{{id}}?refer=web   |  音乐详情，音乐详情ID     |
| snssdk1128://live?room_id={{room_id}}&user_id={{user_id}}&u_code={{u_code}}&from=webview&refer=web   | 直播间     |
| snssdk1128://webview?url={{url}}&from=webview&refer=web   | webview     |
| snssdk1128://webview?url={{url}}&from=webview&hide_nav_bar=1&refer=web   |  webview 沉浸式     |
| snssdk1128://poi/detail?id={{id}}&from=webview&refer=web   | poi详情页     |
| snssdk1128://forward/detail/{{id}}   |  转发详情页     |
| snssdk1128://search | 搜索页面 |
| snssdk1128://search/trending   | 热搜词榜     |
| snssdk1128://search/trending?type=1   | 热搜视频榜     |
| snssdk1128://search/trending?type=2   | 热搜音乐榜     |
| snssdk1128://search/trending?type=3   |  正能量榜     |
| snssdk1128://search/trending?type=4   |  明星榜     |
| snssdk1128://setting | 设置页面 |
| snssdk1128://user/profile | 我的页面 |
| snssdk1128://goods/seeding/?promotion_id={{商品id}} <br />[示例]([1 · Issue #4 · Oct1a/TikTok-Scheme (github.com)](https://github.com/Oct1a/TikTok-Scheme/issues/4#issuecomment-951524650)) | 商品详情 |
| snssdk1128://ec_goods_detail?promotion_id={{商品id}}&enter_from=h5_product_detail&request_additions={"enter_from":"h5_product_detail"} [示例](https://github.com/Oct1a/TikTok-Scheme/issues/4#issuecomment-989526763) | 商品详情 |
| snssdk1128://lynxview/?channel=fe_lynx_commerce_buynow&bundle=app/template.js&use_rifle=1&id={{商品id}}&disable_activity=0&group_id=0&new_source_type=product_detail&status_bar_color=ffffff&loading_bgcolor=ffffff&hide_nav_bar=1&status_font_dark=1&trans_status_bar=0&dynamic=1&c_biz_combo=8&combo_id={{商品型号id}}&combo_num=1 [示例](https://github.com/Oct1a/TikTok-Scheme/issues/4#issuecomment-989525803)  | 商品订单确认页 |
| *snssdk1128://goods*/shop/?uid={{用户id}} | 用户橱窗页 |
| snssdk1128://detail?id={{视频id}}&gd_label=click_schema_yingyongbao | 跳转视频页 |

>  **gd_label:**
>  click_wap_profile_bottom  跳转主页
>  click_wap_download_follow 跳转主页并关注
>  click_wap_profile_feature 跳转视频
>  click_wap_detail_download_feature 打开视频
>
>  **type:**
>  need_follow 需要关注



## 抖音极速版Schema

```
抖音极速版将抖音schema的1128替换成2329即可。
schema = schema.replace(/^snssdk1128/, 'snssdk2329');
```

<br>

## 抖音国际版Schema

```
抖音国际版将抖音schema的1128替换成1233即可。国际版会有些不一样，具体需自测
snssdk1233://user/profile
```



# 快手Schema

| Schema | 描述 |
| -------------------- | ------------------- |
| kwai://home          | 打开首页（启动APP） |
| kwai://gamezone/home | 打开游戏专区        |
| kwai://gamezone/game/[游戏ID] |  打开某个游戏   |
| kwai://webview?url=[URL链接] |  在快手中打开指定URL   |
| kwai://tag/topic/[标签名称]  | 打开标签   |
| kwai://home/following  | 打开关注   |
| kwai://home/hot  | 打开热搜   |
| kwai://promotion | 打开发现    |
| kwai://home/local  | 打开同城   |
| kwai://profile/[用户UID] |  打开用户主页   |
| kwai://profilesetting  | 编辑个人资料   |
| kwai://business/poi  | 地理位置   |
| kwai://business/location  | 定位界面   |
| kwai://work/[作品ID]  | 打开某作品   |
| kwai://work/[照片ID]?userId=[用户ID] |  图片作品    |
| kwai://live/play/[直播房间id] | 直播   |
| kwai://musicstation  | 快手音悦台   |
| kwai://followers  | 粉丝列表   |
| kwai://followings  | 关注列表   |
| kwai://tube/square |  小剧场   |



# 跳转应用商店Scheme/(Market) 

| Scheme                              | 说明                              |  |
| :---------------------------------- | :-------------------------------- | ----------------------------------- |
| market://details?id={{PackageName}} | 通过Java包名直接定位到你的App| 跳转显示App详细介绍页 |
| market://search?q=pname:{{java包名}} | 通过Java包名搜索App | 显示搜索到的App列表 |
| market://search?q=pub:{{开发者名称}} | 通过开发者名称搜索App | 显示开发者发布的所有App列表 |
| market://search?q={{关键词}} | 通过关键词搜索App | 显示搜索到的标题/内容相关的所有App列表 |
| market://search?q={{关键词}}pub:{{开发者名称}} | 组合查询 | 更精确的筛选 |

> 跳转应用商店的market不一定只是官方的市场，如果装有第三方市场也可以由第三方市场检索，个别机型除外。



## 跳转到各大短视频App 作品页 Scheme合集

|      APP       |               Scheme               |
| :------------: | :--------------------------------: |
|  抖音作品页面  | snssdk1128://aweme/detail/[作品id] |
|  快手作品页面  |        kwai://work/[作品id]        |
| 皮皮虾作品页面 | bds://cell_detail?item_id=[作品id] |
|  火山作品页面  |   snssdk1112://item?id=[作品id]    |
|  西瓜作品页面  | snssdk32://detail?groupid=[作品id] |
|  微视作品页面  |   weishi://feed?feed_id=[作品id]   |



## 跳转到各大短视频App 作品页 Scheme合集

|                    |                                     |
| ------------------ | ----------------------------------- |
| 快手用户主页       | kwai://profile/[用户ID]             |
| 微视用户主页       | weishi://profile?person_id=[用户ID] |
| 抖音用户主页       | snssdk1128://user/profile/[用户ID]  |
| 抖音极速版用户主页 | snssdk2329://user/profile/[用户ID]  |



## 微信Schema

| Schema                       | 描述         |
| ---------------------------- | ------------ |
| weixin://dl/scan             | 扫一扫       |
| weixin://dl/feedback         | 反馈         |
| weixin://dl/moments          | 朋友圈       |
| weixin://dl/settings         | 设置         |
| weixin://dl/notifications    | 消息通知设置 |
| weixin://dl/chat             | 聊天设置     |
| weixin://dl/general          | 通用设置     |
| weixin://dl/officialaccounts | 公众号       |
| weixin://dl/games            | 游戏         |
| weixin://dl/help             | 帮助         |
| weixin://dl/feedback         | 反馈         |
| weixin://dl/profile          | 个人信息     |
| weixin://dl/features         | 功能插件     |





## 致谢

感谢[@icesvalley](https://github.com/1965514404) 补充抖音数据（国际版，设置页、商品详情页、订单确认页等）





## 声明

**仅用于技术交流**，互联网不是法外之地，请勿用于不法用途！

