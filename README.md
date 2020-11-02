# TikTok-Scheme
抖音、抖音极速版、tiktok Scheme schemas获取

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
