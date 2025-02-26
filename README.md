# 博客园heart主题修复 (heart-theme-fix)

## 项目简介

本项目为修复博客园(https://www.cnblogs.com/)美化主题heart[https://www.cnblogs.com/yjlaugus/p/13466375.html]

## heart简介
heart[https://www.cnblogs.com/yjlaugus/p/13466375.html]基于主题atum[https://github.com/cjunn/cnblog_theme_atum/]二次开发
如果你想使用本博客主题样式，并希望能得到远程推送更新，只需查看快速部署。在快速部署因为更改了app.js部分源码，功能和原版主题[https://github.com/cjunn/cnblog_theme_atum/]略有差异，若只想改动样式，请查看 只样式引入（建议）。

## 参考资源

- [美化主题atum](https://github.com/cjunn/cnblog_theme_atum)
- [博客园主题快速部署教程](https://www.cnblogs.com/yjlaugus/p/13466375.html)

### 修复原因
- 由于gitee暂停了pages服务，导致静态资源无法访问，atum主题项目地址从gitee变更为GitHub，由于heart主题作者早已经停更，导致heart主题项目无人维护，导致静态资源托管地址失效

### 修复方法
- 将heart主题中所有引用atum主题的gitee静态资源托管地址替换为atum主题的GitHub的项目地址，
  例如https://cjunn.gitee.io/blog_theme_atum/ 替换为 https://cdn.jsdelivr.net/gh/cjunn/cnblog_theme_atum@master/dist/
- heart主题的gitee静态资源托管地址替换为https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/，
  例如https://yjlaugus.gitee.io/blog/cnblogLoader.js 替换为 https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/cnblogLoader.js
- 然后修改heart文件夹内的所有文件输出到heart-theme-fix文件夹内，使其加载GitHub的静态资源


### 项目结构
- cnblog_theme_atum[atum主题]：

其中img为图片素材库,cnblogLoader.js负责从远程服务器加载app.css,app.js,manifest.js,vendor.js文件
在博客园引用cnblogLoader.js前,定义好atum的`staticSrc`、`staticVer`等参数使其cnblogLoader.js加载为您服务器上的静态文件文件。具体可参考下一节介绍。

- heart[heart主题修复前]：

原atum文件夹中的css文件夹与js文件夹被放入releases文件夹中，由img文件夹与releases文件夹组成

- heart-theme-fix[heart主题修复后]：

img文件夹与releases文件夹将要被重新部署到GitHub上，cdn加速地址为：https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/
就是你要输出的修复后的heart主题的文件夹。




heart主题快速部署方法

//请把以下代码粘贴在页首或者侧边栏即可快速部署，若需要更多个性化配置，请继续看下文详细配置
<script type="text/javascript">
(()=>{
let p={};
p.themeStyle = "style1"; //关键配置：主题样式
p.extCss = ["https://blog-static.cnblogs.com/files/yjlaugus/theme.css", "https://at.alicdn.com/t/font_1630741_bf02j4m9mhg.css"];//关键配置：主题样式
p.staticSrc = "https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/releases/"; //关键配置
window.__BLOG_CONFIG__=p;
})();
</script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/cnblogLoader.js"></script>

### 部分配置说明

<script type="text/javascript">
(()=>{
//该处用于配置atum主题参数，具体配置参数可参考
let p={};
p.ingTitle = "憧憬是碎了满地凉凉的宝石，生活是一场大雨留下的潮湿";
p.themeStyle = "style1";
p.feelingBlogId = "12286815"; //某篇随笔文章postid：在文章编辑状态在浏览器地址栏可以看到
p.extCss = ["https://blog-static.cnblogs.com/files/yjlaugus/theme.css", "https://at.alicdn.com/t/font_1630741_bf02j4m9mhg.css"];
p.staticSrc = "https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/releases/";
p.staticIco = "https://images.cnblogs.com/cnblogs_com/yjlaugus/1660383/o_200303114655favicon.png";
p.blogName = "YJLAugus";
p.avatarSign = "向阳而生。";
p.musicIds = [1417862026]; //QQ音乐ID
p.qq = "123456";
p.email = "imyjl@qq.com";
p.github = "YJLAugus";
p.aboutmeHtml = "来自北部的一个小城市，个性不张扬，讨厌随波逐流。";
p.headBackImg = "https://images.cnblogs.com/cnblogs_com/yjlaugus/1280680/o_200124120955leg.png";
p.blogFriendList = [{title: 'YJLAugus', url: 'https://www.cnblogs.com/yjlaugus'},{title: 'NOTE', url: 'https://yjlaugus.github.io'}];     
p.blogUsedLinks = [
{title: '札记', url: 'https://yjlaugus.github.io/'},
{title: '评论管理', url: 'https://yjlaugus.avosapps.us/'}
];
window.__BLOG_CONFIG__=p;
})();
</script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/cnblogLoader.js"></script>

### 只样式引入
<script type="text/javascript">
(()=>{
let p={};
p.themeStyle = "style1"; //关键配置：主题样式
p.extCss = ["https://blog-static.cnblogs.com/files/yjlaugus/theme.css";//关键配置：主题样式
window.__BLOG_CONFIG__=p;
})();
</script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/TechIslands/heart-theme-fix@main/cnblogLoader.js"></script>

### 页面加载动画
粘贴在 页首 即可。

<style type="text/css">body{margin:0;padding:0;overflow:hidden;margin-top:100%}#shade_animal_wrap{opacity:1;margin:0;padding:0;display:flex;position:absolute;top:0;left:0;right:0;bottom:0;align-items:center;justify-content:center;height:100vh;width:100%;background-color:#f2f2f2;z-index:99999;transition:all 1s ease 0s;}.lds-hourglass{display:inline-block;position:relative;width:64px;height:64px;transform:translateX(-30px) translateY(-60px);}.lds-hourglass:after{content:" ";display:block;border-radius:50%;width:0;height:0;margin:6px;box-sizing:border-box;border:60px solid #fff;border-color:#00d9ff transparent #04e2ff transparent;animation:lds-hourglass 1.2s infinite;}@keyframes lds-hourglass{0%{transform:rotate(0);animation-timing-function:cubic-bezier(0.55,0.055,0.675,0.19);}50%{transform:rotate(900deg);animation-timing-function:cubic-bezier(0.215,0.61,0.355,1);}100%{transform:rotate(1800deg);}}</style>
<div id="shade_animal_wrap"><div class="lds-hourglass"></div></div>

### 左侧菜单自定义
p.mainExtNav = [{
title: '主页',
url: 'https://yjlaugus.gitee.io/',
icon: 'iconhome'
}, {
title: '仓库',
url: 'https://github.com/TechIslands/heart-theme-fix',
icon: 'icongithub'
}, {
title: '留言',
url: '/c/subject/p/12286815.html',
icon: 'iconat'
}, {
title: '说说',
url: '/c/author',
icon: 'iconmessage-rounded-alt'
}, {
title: '投喂',
url: '/c/subject/p/7857317.html',
icon: 'iconziyuan'
}];
关于图标您可以在审查元素 找到。

<!-- atum主题急速部署
前提：已经开通js权限，没开通的可以向博客园官方申请开通。

###代码块部署位置

<style type="text/css">
#page_begin_html{top: 0;bottom: 0;left: 0;right: 0;position: fixed;z-index:99999;}
#home #main #mainContent{display:none}
body{margin:0;padding:0;overflow:hidden;margin-top:100%}#shade_animal_wrap{opacity:1;margin:0;padding:0;display:flex;position:absolute;top:0;left:0;right:0;bottom:0;align-items:center;justify-content:center;height:100vh;width:100%;background-color:#f2f2f2;z-index:99999;transition:all .5s ease 0s;}.lds-hourglass{display:inline-block;position:relative;width:64px;height:64px;transform:translateX(-30px) translateY(-60px);}.lds-hourglass:after{content:" ";display:block;border-radius:50%;width:0;height:0;margin:6px;box-sizing:border-box;border:60px solid #fff;border-color:#ff8d00 transparent #ff3004 transparent;animation:lds-hourglass 1.2s infinite;}@keyframes lds-hourglass{0%{transform:rotate(0);animation-timing-function:cubic-bezier(0.55,0.055,0.675,0.19);}50%{transform:rotate(900deg);animation-timing-function:cubic-bezier(0.215,0.61,0.355,1);}100%{transform:rotate(1800deg);}}</style>
<div id="shade_animal_wrap"><div class="lds-hourglass"></div></div>
将上述代码块拷贝至 博客园设置->页首HTML代码 。

<script>
$("link").remove();$("script").remove();$(function(){$("link").remove();$("script").remove()});window.blogCommentManager=function(){this.renderComments=function(){}};window.loadViewCount=function(){};window.loadNewsAndKb=function(){};window.loadBlogSignature=function(){};window.LoadPostCategoriesTags=function(){};window.LoadPostInfoBlock=function(){};window.GetPrevNextPost=function(){};window.loadBlogCalendar=function(){};window.loadBlogSideColumn=function(){};window.loadBlogTopLists=function(){};window.GetHistoryToday=function(){};window.deliverAdT2=function(){};window.getFollowStatus=function(){};window.deliverAdC1=function(){};
</script>
<script type="text/javascript">
(()=>{
//该处用于配置atum主题参数，具体配置参数可参考下方。
let p={};
p.blogSign="自惭多情污梵行，入山又恐误倾城。世间安得双全法，不负如来不负卿。";
p.avatarSign= " ↗↗点击头像关注我。";
window.__BLOG_CONFIG__=p;

})();
</script>
<script type=text/javascript src=https://cdn.jsdelivr.net/gh/cjunn/cnblog_theme_atum@master/dist/cnblogLoader.js></script>
将上述代码块拷贝至 博客园设置->博客侧边栏公告（支持HTML代码） （支持 JS 代码） ，并且按需配置好所需要的参数并且赋值给全局变量__BLOG_CONFIG__中。

###可配置的相关参数

//音乐请求接口API地址
let musicApiUrl = "https://api.i-meto.com/meting/api?server=netease&type=:type&id=:id&r=:r";
//扩展素材库地址根路径
let extendStylePath = "https://cdn.jsdelivr.net/gh/cjunn/cnblog_theme_atum@master/dist/"
//作者页背景图片地址URL
let headBackImg = `${extendStylePath}/img/ing/autorbimg.jpg`;
//首页背景图片地址URL
let bigBackImg = `${extendStylePath}/img/body/background.jpg`;
//文章块前置图片URL，数组[]。
let panelItemPic=Array.from(Array(35), (v,k) => (`${extendStylePath}/img/pageItem/page-item-$I.jpg`).replace("$I",k+1));
//右侧快速导航图片URL，数组[]
let panelRightImgPic=Array.from(Array(10), (v,k) =>(`${extendStylePath}/img/menuIcon/menuicon-$I.png`).replace("$I",k));
//默认音乐播放器音乐图片URL
let musicSignImg=`${extendStylePath}/img/body/music_play.png`;
//博客签名
let blogSign = "自惭多情污梵行，入山又恐误倾城。世间安得双全法，不负如来不负卿。";
//作者页关于我 HTML
let aboutmeHtml = `<img src='${extendStylePath}/img/ing/aboutme.jpg'/>`;
//作者签名
let avatarSign = " ↗↗点击头像关注我。";
//心情栏签名
let ingTitle = "你的一字一句犹如刀疤划心上，我的一举一动随你改变多荒唐。";
//友链
let blogFriendList = [];                      //{name: '', url: ''}格式
//暂时无用
let blogUsedLinks = [];                       //{name: '', url: ''}格式
//网易云音乐ID ，数组[]
let musicIds = ["1382596189"];
let qq = "592571519";
let email = "592571519@qq.com"
let github = "cjunn";
//评论人默认图片URL
let defHeadImg= `${extendStylePath}/img/body/defAvatar.jpg`;
//默认采用主题风格，style0、style1可选。
let themeStyle="style0";
//用于心情展示的博客ID
let feelingBlogId=13393903;
//导航链接
let mainExtNav = [
  {title: "首页",url:"/subject/category/default.html",icon: "home"},
  {title: "博客动态", url: "https://www.cnblogs.com/cjunn/", icon: "comment1"},
  {title: "博主简历", url: "https://www.cnblogs.com/cjunn/", icon: "face2"},
  {title: "主题反馈", url: '/c/subject/p/12494785.html', icon: "bug"},
  {title: "赞赏博主", url: '/c/subject/p/12495086.html', icon: "gift"}
];
//广告栏的HTML
let adDisplay="<div class=\"blog-cloud-ad-item\">\n" +
  "            <img src=\"https://img.alicdn.com/tfs/TB1nkoQDlv0gK0jSZKbXXbK2FXa-440-240.jpg\"\n" +
  "                 onclick=\"window.open('https://www.aliyun.com/activity/daily/cloud?userCode=njf7bpon')\">\n" +
  "          </div>\n" +
  "          <div class=\"blog-cloud-ad-item\">\n" +
  "            <img src=\"https://upload-dianshi-1255598498.file.myqcloud.com/345-60759ea0b2a21d3d1c764570c2a9f2960bfdf128.200.jpg\"\n" +
  "                 onclick=\"window.open('https://url.cn/OLi4lNzq')\">\n" +
  "          </div>";
上方是可配置的参数目前的默认参数值。可以根据目前自己所需要的修改相关参数值，然后设置进全局参数__BLOG_CONFIG__中。 -->
