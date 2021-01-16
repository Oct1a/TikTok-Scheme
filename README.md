# TikTok-Scheme
抖音、抖音极速版、tiktok Scheme schemas获取，将持续更新

```
// gd_label是唤起应用时，通知客户端记录打点的字段
// gd_label参数： https://wiki.bytedance.net/pages/viewpage.action?pageId=179404954
// gd_label的值有哪些： https://docs.google.com/spreadsheets/d/1EWzh4gIbE861d9Rbk-M7QNYCPnltkNt9r2ETVSV2wf4/edit#gid=2126697475
  home: 'snssdk1128://feed?refer=web&gd_label={{gd_label}}',// 首页feed
  detail: 'snssdk1128://aweme/detail/{{id}}?refer=web&gd_label={{gd_label}}&appParam={{appParam}}&needlaunchlog=1',// 作品详情页
  user: 'snssdk1128://user/profile/{{uid}}?refer=web&gd_label={{gd_label}}&type={{type}}&needlaunchlog=1',// 用户主页
  challenge: 'snssdk1128://challenge/detail/{{id}}?refer=web&is_commerce=0',// 挑战详情
  music: 'snssdk1128://music/detail/{{id}}?refer=web',// 音乐详情
  live: 'snssdk1128://live?room_id={{room_id}}&user_id={{user_id}}&u_code={{u_code}}&from=webview&refer=web',// 直播间
  webview: 'snssdk1128://webview?url={{url}}&from=webview&refer=web',// webview
  webview_fullscreen: 'snssdk1128://webview?url={{url}}&from=webview&hide_nav_bar=1&refer=web',// webview 沉浸式
  poidetail: 'snssdk1128://poi/detail?id={{id}}&from=webview&refer=web',// poi详情页
  forward: 'snssdk1128://forward/detail/{{id}}', // 转发详情页
  billboard_word: 'snssdk1128://search/trending', // 热搜词榜
  billboard_video: 'snssdk1128://search/trending?type=1', // 热搜视频榜
  billboard_music: 'snssdk1128://search/trending?type=2',// 热搜音乐榜
  billboard_positive: 'snssdk1128://search/trending?type=3',// 正能量榜
  billboard_star: 'snssdk1128://search/trending?type=4' // 明星榜
```
抖音极速版
```
// 抖音极速版替换appid
    schema = schema.replace(/^snssdk1128/, 'snssdk2329');
```
ios内部schema是aweme开头，所提替换链接上的schema为 aweme 开头

/* ios
            微信中，下载短链302到应用宝，同时universal link会302到 snssdk143://xx，而微信会屏蔽snssdk143://这种非http协议，
            由于两者时间很短，几乎同时，似乎对短链的302也屏蔽的，（不太了解机制），所以两者时间上要有一定的间隔。
            由于下载短链在当前页面打开应用宝页面，就不会执行后面的代码，所以先进行跳转
            */

 qq空间无法唤起（下载）app， qq会话窗口可以，但是无法区别是从qq会话还是空间打开的页面
    // 所以在qq内，使用一个弹层引导用户在其它浏览器打开页面

```
获取用户信息
/web/api/v2/user/info/?sec_uid={{sec_uid}}
```



# 快手Schema

|                 |                     |
| --------------- | ------------------- |
| kwai://home     | 打开首页（启动APP） |
| ksthanos://home |                     |
|                 |                     |



# 跳转应用商店

market://details?id={{PackageName}}





快手

kwai://gamezone/home 打开游戏专区
kwai://gamezone/game/[游戏ID] 打开某个游戏
kwai://webview?url=[URL链接] 在快手中打开指定URL
kwai://tag/topic/[标签名称] 打开标签
kwai://home/following 打开关注
kwai://home/hot 打开热搜
kwai://promotion打开发现 
kwai://home/local 打开同城
kwai://profile/[用户UID] 打开用户主页
kwai://profilesetting 编辑个人资料
kwai://business/poi 地理位置
kwai://business/location 定位界面
kwai://work/[作品ID] 打开某作品
kwai://work/[PhotoId]?userId=[UserId] 图片作品 
kwai://live/play/[LiveStreamId] 直播
kwai://liveaggregate?sourceType=[不知道什么参数]
kwai://liveaggregate/[未知参数]?sourceType=[未知参数]
kwai://musicstation/[PhotoId]?userId=[UserId]&sourceType=[Integer.valueOf(13)]
kwai://musicstation 快手音悦台
kwai://followers 粉丝列表
kwai://followings 关注列表
kwai://tube/square 小剧场



微信

weixin://dl/scan 扫一扫
weixin://dl/feedback 反馈
weixin://dl/moments 朋友圈
weixin://dl/settings 设置
weixin://dl/notifications 消息通知设置
weixin://dl/chat 聊天设置
weixin://dl/general 通用设置
weixin://dl/officialaccounts 公众号
weixin://dl/games 游戏
weixin://dl/help 帮助
weixin://dl/feedback 反馈
weixin://dl/profile 个人信息
weixin://dl/features 功能插件