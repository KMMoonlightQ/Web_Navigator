<template>
  <div class="home">
    <div class="navigator">
      <div class="title">
        <div class="title_top">
          <span>KMMoonlight的导航页</span>
        </div>
        <div class="title_bottom">
          Tools for Navigator
        </div>
      </div>

      <div class="category">
        <ul>
          <li v-for="item in items" v-on:click="ScrollToTarget(item.CategoryName)">
            <a-icon v-bind:type="item.CategoryType"></a-icon>
            <span>{{ item.CategoryName }}</span>
          </li>
        </ul>
      </div>
    </div>

    <div class="content">
       <ul>
         <li v-for="(item, index) in stationArray" v-bind:key="index">
           <NavigatorItem
                   :category-name="item.CategoryName"
                   :station-array="item.StationArray"
           >
           </NavigatorItem>
         </li>
       </ul>
    </div>
  </div>
</template>

<script lang="ts">
import {Vue, Component} from 'vue-property-decorator';
import NavigatorItem from '../components/NavigatorItem.vue';

@Component({
  name : "Home",
  components : {
    NavigatorItem
  },
})
export default class Home extends Vue {


  private items = [
    {
      "CategoryName" : "搜索引擎",
      "CategoryType" : "search",
    },
    {
      "CategoryName" : "常用工具",
      "CategoryType" : "tool",
    },
    {
      "CategoryName" : "学习教程",
      "CategoryType" : "book",
    },
    {
      "CategoryName" : "视频网站",
      "CategoryType" : "play-circle",
    },
    {
      "CategoryName" : "技术文档",
      "CategoryType" : "file",
    },
    {
      "CategoryName" : "娱乐生活",
      "CategoryType" : "customer-service",
    }
  ]

  private stationArray = [
    {
      "CategoryName" : "搜索引擎",
      "StationArray" : [
        {
          "siteName" : "Google",
          "siteDesc" : "Google搜索速度极快，网页数量在搜索引擎中名列前茅",
          "siteUrl"  : "https://www.google.com.hk",
          "siteAlias": require("../assets/imgs/google.png")
        },
        {
          "siteName" : "百度",
          "siteDesc" : "百度搜索依托专业垂直频道，随时随地使用百度搜索服务",
          "siteUrl"  : "https://www.baidu.com",
          "siteAlias": require("../assets/imgs/baidu.png")
        },
        {
          "siteName" : "秘迹搜索",
          "siteDesc" : "这是一个不追踪你的搜索引擎",
          "siteUrl"  : "https://mijisou.com/",
          "siteAlias": require("../assets/imgs/miji.png")
        },
        {
          "siteName" : "dogedoge",
          "siteDesc" : "不追踪，不误导",
          "siteUrl"  : "https://www.dogedoge.com/",
          "siteAlias": require("../assets/imgs/dogedoge.png")
        }
      ],
    },
    {
      "CategoryName" : "常用工具",
      "StationArray" : [
        {
          "siteName" : "IconFont",
          "siteDesc" : "阿里巴巴矢量图标库",
          "siteUrl"  : "https://www.iconfont.cn/",
          "siteAlias": require("../assets/imgs/iconfont.png")
        },
        {
          "siteName" : "语雀",
          "siteDesc" : "面向个人和团队，提供与众不同的知识管理",
          "siteUrl"  : "https://www.yuque.com/",
          "siteAlias": require("../assets/imgs/yuque.png")
        },
        {
          "siteName" : "超能搜",
          "siteDesc" : "强大的网盘搜索工具",
          "siteUrl"  : "http://www.chaonengsou.com/",
          "siteAlias": require("../assets/imgs/chaonengsou.png")
        },
        {
          "siteName" : "鱼塘",
          "siteDesc" : "究极摸鱼工具网站",
          "siteUrl"  : "https://mo.fish/main/home/hot",
          "siteAlias": require("../assets/imgs/fish.png")
        },
        {
          "siteName" : "LeetCode",
          "siteDesc" : "算法，刷题，是时候展现真正的技术了！",
          "siteUrl"  : "https://leetcode-cn.com/",
          "siteAlias": require("../assets/imgs/leetcode.png")
        },
        {
          "siteName" : "V2EX",
          "siteDesc" : "创意工作者们的社区",
          "siteUrl"  : "https://v2ex.com/",
          "siteAlias": require("../assets/imgs/v2ex.png")
        },
        {
          "siteName" : "CodeKK",
          "siteDesc" : "强大的Android第三方库查询搜索工具网站",
          "siteUrl"  : "https://p.codekk.com/",
          "siteAlias": require("../assets/imgs/codekk.png"),
        },
        {
          "siteName" : "TalkingData",
          "siteDesc" : "领先的移动端数据分析平台",
          "siteUrl"  : "http://www.talkingdata.com/",
          "siteAlias": require("../assets/imgs/talkingdata.png")
        },
        {
          "siteName" : "蓝湖",
          "siteDesc" : "高效的产品设计协作平台",
          "siteUrl"  : "https://lanhuapp.com/",
          "siteAlias": require("../assets/imgs/lanhu.png")
        },
        {
          "siteName" : "墨刀",
          "siteDesc" : "专业、可靠、简洁、易懂的在线产品原型设计与协作平台",
          "siteUrl"  : "https://modao.cc/",
          "siteAlias": require("../assets/imgs/modao.png")
        },
        {
          "siteName" : "石墨文档",
          "siteDesc" : "全新一代云端 Office，面向未来的办公软件",
          "siteUrl"  : "https://shimo.im/welcome",
          "siteAlias": require("../assets/imgs/shimo.png")
        },
        {
          "siteName" : "谷歌翻译",
          "siteDesc" : "目前最好的翻译软件",
          "siteUrl"  : "https://translate.google.cn/",
          "siteAlias": require("../assets/imgs/fanyi.png")
        },
        {
          "siteName" : "GitHub",
          "siteDesc" : "全球最大的同性交友网站",
          "siteUrl"  : "https://github.com/",
          "siteAlias": require("../assets/imgs/github.png")
        },
        {
          "siteName" : "掘金",
          "siteDesc" : "一个帮助开发者成长的社区",
          "siteUrl"  : "https://juejin.im/",
          "siteAlias": require("../assets/imgs/juejin.png")
        },
        {
          "siteName" : "Docsify",
          "siteDesc" : "Markdown文档生成工具",
          "siteUrl"  : "https://docsify.js.org/#/zh-cn/",
          "siteAlias": require("../assets/imgs/docsify.png")
        },
        {
          "siteName" : "RssHub",
          "siteDesc" : "一个开源、简单易用、易于扩展的 RSS 生成器",
          "siteUrl"  : "https://docs.rsshub.app/",
          "siteAlias": require("../assets/imgs/rsshub.png")
        },
        {
          "siteName" : "百度地图",
          "siteDesc" : "方便规划交通路线",
          "siteUrl"  : "https://map.baidu.com/",
          "siteAlias": require("../assets/imgs/baidumap.png")
        },
        {
          "siteName" : "什么值得买",
          "siteDesc" : "不知道是增加了消费还是减少了消费",
          "siteUrl"  : "https://www.smzdm.com/",
          "siteAlias": require("../assets/imgs/smzdm.png")
        },
        {
          "siteName" : "播客订阅",
          "siteDesc" : "播客越来越成为一种有效获取信息的渠道",
          "siteUrl"  : "https://getpodcast.xyz/",
          "siteAlias": require("../assets/imgs/boke.png")
        },
        {
          "siteName" : "MSDN I Tell You",
          "siteDesc" : "微软下载资源大合集",
          "siteUrl"  : "https://msdn.itellyou.cn/",
          "siteAlias": require("../assets/imgs/itellyou.png")
        }
      ]
    },
    {
      "CategoryName" : "学习教程",
      "StationArray" : [
        {
          "siteName" : "SpringBoot参考指南",
          "siteDesc" : "SpringBoot指南教程",
          "siteUrl"  : "https://qbgbook.gitbooks.io/spring-boot-reference-guide-zh/content/",
          "siteAlias": require("../assets/imgs/gitbook.png")
        },
        {
          "siteName" : "SpringBoot2.x教程",
          "siteDesc" : "SpringBoot2.x系列教程",
          "siteUrl"  : "https://www.bysocket.com/springboot",
          "siteAlias": require("../assets/imgs/springboot2.png")
        },
        {
          "siteName" : "Django教程",
          "siteDesc" : "Django中文网系列教程",
          "siteUrl"  : "https://www.django.cn/article/",
          "siteAlias": require("../assets/imgs/django.png")
        },
        {
          "siteName" : "廖雪峰Python教程",
          "siteDesc" : "大佬的Python入门教程",
          "siteUrl"  : "https://www.liaoxuefeng.com/wiki/1016959663602400",
          "siteAlias": require("../assets/imgs/liaoxuefeng.png")
        },
        {
          "siteName" : "A Bite Of Python",
          "siteDesc" : "咬一口Python，大佬学习Python时积累的经验知识。",
          "siteUrl"  : "https://www.liaoxuefeng.com/wiki/1016959663602400",
          "siteAlias": require("../assets/imgs/github.png")
        },
        {
          "siteName" : "扔物线",
          "siteDesc" : "Android自定义View教程",
          "siteUrl"  : "https://hencoder.com/",
          "siteAlias": require("../assets/imgs/hencoder.png")
        },
        {
          "siteName" : "马上开学",
          "siteDesc" : "Android Kotlin教程",
          "siteUrl"  : "https://kaixue.io/",
          "siteAlias": require("../assets/imgs/kaixue.png")
        },
        {
          "siteName" : "Flutter教程",
          "siteDesc" : "Flutter中文网Start",
          "siteUrl"  : "https://flutterchina.club/get-started/install/",
          "siteAlias": require("../assets/imgs/flutter.png")
        },
        {
          "siteName" : "Flutter实战",
          "siteDesc" : "Flutter中文网社区创办者编写的Flutter教程书籍",
          "siteUrl"  : "https://book.flutterchina.club/",
          "siteAlias": require("../assets/imgs/gitbook.png")
        },
      ]
    },
    {
      "CategoryName" : "视频网站",
      "StationArray" : [
        {
          "siteName" : "网易云课堂",
          "siteDesc" : "网易云课堂，一个专注职业技能提升的在线学习平台。",
          "siteUrl"  : "https://study.163.com/",
          "siteAlias": require("../assets/imgs/study163.png")
        },
        {
          "siteName" : "慕课网",
          "siteDesc" : "程序员的梦工厂",
          "siteUrl"  : "https://www.imooc.com/",
          "siteAlias": require("../assets/imgs/imooc.png")
        },
        {
          "siteName" : "TopBook",
          "siteDesc" : "高效生活视频书",
          "siteUrl"  : "https://topbook.cc/overview",
          "siteAlias": require("../assets/imgs/topbook.png")
        }
      ],
    },
    {
      "CategoryName" : "技术文档",
      "StationArray" : [
        {
          "siteName" : "树莓派实验室",
          "siteDesc" : "树莓派（Raspberry Pi）中文资讯站，提供丰富的树莓派教程和DIY资讯。",
          "siteUrl"  : "https://shumeipai.nxez.com/",
          "siteAlias": require("../assets/imgs/shumeipai.png")
        },
        {
          "siteName" : "Kotlin文档",
          "siteDesc" : "Kotlin官方文档翻译",
          "siteUrl"  : "https://hltj.gitbooks.io/kotlin-reference-chinese/content/",
          "siteAlias": require("../assets/imgs/gitbook.png")
        },
        {
          "siteName" : "SpringBoot2.x文档",
          "siteDesc" : "SpringBoot2.x官方文档翻译",
          "siteUrl"  : "https://docshome.gitbooks.io/springboot/content/",
          "siteAlias": require("../assets/imgs/gitbook.png")
        },
        {
          "siteName" : "Vue.js",
          "siteDesc" : "Vuejs官方文档",
          "siteUrl"  : "https://cn.vuejs.org/v2/guide/",
          "siteAlias": require("../assets/imgs/vue.png")
        },
        {
          "siteName" : "iView",
          "siteDesc" : "iView官方文档",
          "siteUrl"  : "https://www.iviewui.com/docs/guide/install",
          "siteAlias": require("../assets/imgs/iView.png")
        },
        {
          "siteName" : "Element",
          "siteDesc" : "Element官方文档",
          "siteUrl"  : "https://element.eleme.cn/#/zh-CN/component/quickstart",
          "siteAlias": require("../assets/imgs/element.png")
        },
        {
          "siteName" : "TypeScript",
          "siteDesc" : "TypeScript官方文档",
          "siteUrl"  : "https://www.tslang.cn/docs/home.html",
          "siteAlias": require("../assets/imgs/ts.png")
        },
        {
          "siteName" : "Scrapy",
          "siteDesc" : "Scrapy官方文档",
          "siteUrl"  : "https://scrapy-chs.readthedocs.io/zh_CN/latest/index.html",
          "siteAlias": require("../assets/imgs/guide.png")
        },
        {
          "siteName" : "DRF",
          "siteDesc" : "django-rest-framework官方文档",
          "siteUrl"  : "https://www.django-rest-framework.org/",
          "siteAlias": require("../assets/imgs/drf.png")
        },
        {
          "siteName" : "BeautifulSoup",
          "siteDesc" : "BeautifulSoup官方文档",
          "siteUrl"  : "https://www.crummy.com/software/BeautifulSoup/bs4/doc/index.zh.html",
          "siteAlias": require("../assets/imgs/guide.png")
        },
        {
          "siteName" : "flask",
          "siteDesc" : "flask官方文档",
          "siteUrl"  : "https://dormousehole.readthedocs.io/en/latest/",
          "siteAlias": require("../assets/imgs/flask.png")
        },
        {
          "siteName" : "Dart",
          "siteDesc" : "Dart2官方文档",
          "siteUrl"  : "https://www.kancloud.cn/marswill/dark2_document/709087",
          "siteAlias": require("../assets/imgs/dart.png")
        },
        {
          "siteName" : "RxVolley",
          "siteDesc" : "Android网络请求库RxVolley官方文档",
          "siteUrl"  : "http://rxvolley.mydoc.io/?t=148787",
          "siteAlias": require("../assets/imgs/guide.png")
        },
        {
          "siteName" : "OkGo",
          "siteDesc" : "Android网络请求库OkGo官方文档",
          "siteUrl"  : "https://github.com/jeasonlzy/okhttp-OkGo/wiki/OkGo",
          "siteAlias": require("../assets/imgs/github.png")
        },
        {
          "siteName" : "Retrofit",
          "siteDesc" : "Android网络请求库Retrofit官方文档",
          "siteUrl"  : "https://square.github.io/retrofit/",
          "siteAlias": require("../assets/imgs/github.png")
        },
        {
          "siteName" : "Fresco",
          "siteDesc" : "强大的Android图片加载库官方文档",
          "siteUrl"  : "https://www.fresco-cn.org/docs/getting-started.html",
          "siteAlias": require("../assets/imgs/github.png")
        },
        {
          "siteName" : "Ant Design For Vue",
          "siteDesc" : "Ant Design Vue版官方文档",
          "siteUrl"  : "http://vue.ant-design.cn/docs/vue/introduce-cn/",
          "siteAlias": require("../assets/imgs/github.png")
        }
      ],
    },
    {
      "CategoryName" : "娱乐生活",
      "StationArray" : [
        {
          "siteName" : "Bilibili",
          "siteDesc" : "哔哩哔哩 (゜-゜)つロ 干杯~-bilibili",
          "siteUrl"  : "https://www.bilibili.com/",
          "siteAlias": require("../assets/imgs/bilibili.png")
        },
        {
          "siteName" : "斗鱼直播",
          "siteDesc" : "每个人的直播平台",
          "siteUrl"  : "https://www.douyu.com/",
          "siteAlias": require("../assets/imgs/douyu.png")
        },
        {
          "siteName" : "虎牙直播",
          "siteDesc" : "弹幕式互动直播平台",
          "siteUrl"  : "https://www.huya.com/",
          "siteAlias": require("../assets/imgs/huya.png")
        },
        {
          "siteName" : "Steam",
          "siteDesc" : "G胖，阀门印钞机",
          "siteUrl"  : "https://store.steampowered.com/",
          "siteAlias": require("../assets/imgs/steam.png")
        },
        {
          "siteName" : "机核网 Gcores",
          "siteDesc" : "深入探讨游戏相关文化",
          "siteUrl"  : "https://www.gcores.com/",
          "siteAlias": require("../assets/imgs/gcores.png")
        },
        {
          "siteName" : "NGA社区",
          "siteDesc" : "精英玩家撕逼俱乐部",
          "siteUrl"  : "http://bbs.nga.cn/",
          "siteAlias": require("../assets/imgs/nga.png")
        },
        {
          "siteName" : "游研社",
          "siteDesc" : "游戏内容新媒体",
          "siteUrl"  : "https://www.yystv.cn/",
          "siteAlias": require("../assets/imgs/yys.png")
        },
        {
          "siteName" : "TapTap",
          "siteDesc" : "貌似是要成为手机端的Steam",
          "siteUrl"  : "https://www.taptap.com/",
          "siteAlias": require("../assets/imgs/taptap.png")
        },
        {
          "siteName" : "豆瓣",
          "siteDesc" : "文艺青年专用",
          "siteUrl"  : "https://www.douban.com/",
          "siteAlias": require("../assets/imgs/douban.png")
        },
        {
          "siteName" : "微博",
          "siteDesc" : "当好吃瓜群众",
          "siteUrl"  : "https://weibo.com/",
          "siteAlias": require("../assets/imgs/weibo.png")
        },
        {
          "siteName" : "知乎",
          "siteDesc" : "知乎，分享你刚编的故事",
          "siteUrl"  : "https://www.zhihu.com/",
          "siteAlias": require("../assets/imgs/zhihu.png")
        },
        {
          "siteName" : "百度贴吧",
          "siteDesc" : "全球最大的中文社区--全球最大的撕逼社区",
          "siteUrl"  : "https://tieba.baidu.com/",
          "siteAlias": require("../assets/imgs/baidu.png")
        },
        {
          "siteName" : "喜马拉雅FM",
          "siteDesc" : "有声小说，在线电台，有声书",
          "siteUrl"  : "https://www.ximalaya.com/",
          "siteAlias": require("../assets/imgs/xmly.png")
        },
        {
          "siteName" : "微信读书",
          "siteDesc" : "备受好评的微信读书网页版",
          "siteUrl"  : "https://weread.qq.com/",
          "siteAlias": require("../assets/imgs/wxds.png")
        },
        {
          "siteName" : "网易云音乐",
          "siteDesc" : "专注发现与分享的音乐产品，打造全新的音乐社交",
          "siteUrl"  : "https://music.163.com/",
          "siteAlias": require("../assets/imgs/music.png")
        },
      ],
    },


  ];

  private ScrollToTarget(id: string) {
    const elem = document.querySelector("#" + id);
    if (elem !== null) {
      elem.scrollIntoView({behavior: 'smooth'});
    }
    return elem;
  }
}


</script>


<style>
* {
  margin:0;
  padding:0
}

li {
  list-style:none
}

img {
  vertical-align:top;
  border:none
}


.home {
  display: flex;
  display: -webkit-flex;
  width: 100%;
}

.navigator {
  width: 260px;
  background-color: #2C2E2F;
  display: flex;
  flex-direction: column;
  height: 1000px;
  position: fixed;
}

.content {
  margin-left: 260px;
  flex: 1;
  background-color: #F2F2F2;
  height: 100%;
}

.title {
  display: flex;
  flex-direction: column;
  width: 100%;
  align-items: center;
}

.title_top {
  margin-top: 10px;
  font-size: 22px;
  color: #FFFFFF;
}

.title_bottom {
  margin-top: 5px;
  font-size: 16px;
  color: #FFFFFF;
}

.category {
  margin-top: 20px;
}

.category li{
  font-size: 14px;
  color: #979898;
  margin: 30px 0px 30px 40px;
}

.category li:hover {
  color: #FFFFFF;
}

.category span {
  margin-left: 10px;
}



</style>