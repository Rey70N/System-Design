
# [系统设计面试](https://github.com/stevenli91748/System-Design/blob/master/Interview/README.md)

# 目录

#  System-Design

 * [近二十年技术发展：从集中式架构到云原生架构](https://blog.csdn.net/weixin_44326589/article/details/93894615)
 
 <a href="https://ibb.co/M53YF64"><img src="https://i.ibb.co/DgSx0py/6ee62597-6d98-4af5-93b4-bc54f97c7936.png" alt="6ee62597-6d98-4af5-93b4-bc54f97c7936" border="0"></a>
 
* [集中式架构与分布式架构比较](https://blog.csdn.net/qq_27384769/article/details/80223473) 
* [单体式架构和分布式架构有什么区别？](https://blog.csdn.net/weixin_43941991/article/details/86519491)
* [服务器虚拟化技术简介](https://www.cnblogs.com/yogurtwu/p/9989200.html)
* [Docker容器化组件架构](https://www.jdon.com/artichect/docker-containerization.html)
* [云原生技术和架构概述](https://blog.csdn.net/BtB5e6Nsu1g511Eg5XEg/article/details/86326182)

--- 
 
 软件架构是软件系统的顶层结构，架构设计目的就是**解决软件系统复杂度（高性能 高可用 可扩展）**
 
 没有设计的思想，你就不能成为一名架构师。架构师是一个能撸的了一手好代码，画的了一个漂亮的UML/原型，写的了一篇技术文档，更加能解决好项目关键技术的综合人才。架构师=前端工程师+后端程序员+系统分析师+关键技术解决+各种技术搭配+设计模式+部署调优+其他，可见架构师是多面手，在项目当中起到连接管理与项目成员的重要角色。因此，在通往大神级的架构师的道路上，**你需要懂需求、设计、代码、部署、架构、服务器、运维、调优等等。**
 
 一个能担负起企业级应用的架构师，脑海里常出现的词会是这些：负载均衡、集群、分布式、高并发、高可用、易管理等等，粗略说来，应具备以下知识技能：



（1）数据层：重点在于集群方案的选择，比如MySQL集群，集群方案很多，需要选择符合业务的方案，比如多主，主备，读写分离等等，是否还需要做高可用，是用lvs，还是zookeeper，是否需要例如mycat类中间件来管理数据库或者做数据分片等等。

（2）服务层：时髦一点，选择dubbo，微服务让团队开发耦合度没有那么高，各自关心各自的模块，都以服务方式发布出去。传统一点用springmvc+restful，在我看来，对于并发不高的系统，没有必要用dubbo。缓存的选择，涉及到文件缓存、数据库缓存，可以用memcached、ehcache、redis。

（3）应用层：框架太多，ssh,ssm,jfinal等等，选择适合项目团队的框架；UI界面，h5很美观，但对于浏览器的兼容就把开发人员搞哭了，可以选择成熟的ext或者easyui。

（4）网络层：多数开发人员都不用涉及，能了解下f5之类的就好。

（5）部署：是否需要用docker来部署，开源docker容器让部署轻量化，很容易就可以扩展一个节点，对于高并发、伸缩性要求高的场景可以使用。docker的出现，完全可以实现一键部署。是否需要负载均衡，可以选择硬负载（就是前面说的f5），也可以用软负载（nginx）。软负载的方案简单一点可以是apache+tomcat，需要考虑session复制，复杂一点选择lvs+haproxy。打包发布，熟练使用maven，能建立自己的maven私服，能指导项目成员使用maven打包发布。

（6）安全：大多数安全在网络层就解决了，但应用的安全不容忽视，比如需要考虑SQL注入，授权认证，这些目前框架都能解决，重点的安全问题来自框架本身，大多数应用选择框架都是开源的，如果团队没有能力修复漏洞只能等更新。

（7）其它方面：测试（自动化测试），版本管理（git or svn)，大数据（奇热无比），人工智能（高大上）等等。

有人问，架构师为什么还要写代码？我认为，需要一如既往的写，但写的目标不一样，理论水平和动手能力需要同时提高。深度方面，注重的设计思想和模式；广度方面，对于前沿技术，要不懈的追求和钻研，这样才能在未来技术架构选型做出合理的决策。

这里为大家分享一个学习路线：

**依次是开源框架解析专题---架构师筑基专题----高性能架构专题----微服务架构专题----团队协作开发专题----B2C商城实战专题**


# 1. 需求

### [1.1 软件需求规划](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/软件需求规划/README.md)
  
### [1.2 软件需求开发](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/软件需求开发/README.md)

### [1.3 邻域建模](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/邻域建模/README.md)

### [1.4 确定关键需求](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/确定关键需求/README.md)

 
# 2. 设计

## 架构设计三原则
   * 合适原则
   * 简单原则
   * 演化原则

## [概念架构设计](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/概念架构设计/README.md)

  * 2.1 功能性设计
  
  * 2.2 非功能性设计
  
    系统非功能性设计的6个复杂度
    
    * 2.2.1.  [高性能架构](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/README.md)
    * 2.2.2.  [高可用性架构](https://github.com/stevenli91748/System-Design/blob/master/High%20availability%20architecture/README.md)
    * 2.2.3.  [高伸缩性架构](https://github.com/stevenli91748/System-Design/blob/master/Highly%20scalable%20architecture/README.md)
    * 2.2.4.  [高櫎展性架构](https://github.com/stevenli91748/System-Design/blob/master/高櫎展性架构/README.md)
    * 2.2.5.  高安全性架构
    * 2.2.6.  [高并发架构](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/README.md)

## [细化架构设计](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/细化架构设计/README.md)

## [架构验证]()

---

## 互联网系统架构模板

<a href="https://ibb.co/RCmqnhQ"><img src="https://i.ibb.co/XzgqByF/1-2.png" alt="1-2" border="0"></a>

### 采用RESTful API 技术
<p align="center">
  <img src="http://i.imgur.com/jj3A5N8.png">
  <br/>
</p>

---

### 采用微服务技术 + RESTful API 技术

![Imgur](http://i.imgur.com/jrUBAF7.png)

### 2.1. 前端架构
   * [DNS (Domain Name System)  ](https://github.com/stevenli91748/System-Design/blob/master/DNS/README.md)
     * DNS轮询
     * 智能DNS
   * 动静分离--静态资源独立部署
   * 图片服务
   * [CDN (Content Delivery Network)](https://github.com/stevenli91748/System-Design/blob/master/CDN/README.md)
      * [Push CDNs]
      * [Pull CDNs]
   * [反向代理](https://github.com/stevenli91748/System-Design/blob/master/Reverse%20Proxy/README.md)
   * GSLB全局负载均衡
### 2.2. 应用层架构
   * 开发框架
   * 用户层技术
     * 用户管理
       * SSO---单点登录
         * cookie
         * token
         * CAS
       * OAuth2.0---授登录  
     * 消息推送
       * 短信
       * 邮件
       * 站内信
       * App 推送
     * 图片云
     * 存储云
   * 业务层技术
     * 搜索引擎
     * 推荐系统
   * 页面渲染--API Gateway
       * [API Gateway](https://github.com/stevenli91748/System-Design/blob/master/APIGateWay/README.md)
       * [Writing API]
       * [Reading API]
       * [Searching API]
   * [负载均衡](https://github.com/stevenli91748/System-Design/blob/master/Load%20%20Balance/README.md)
   * Session管理
   * 动态页面静态化
   * 业务拆分
   * 虚拟化服务器
#### 2.3. [服务层架构](https://github.com/stevenli91748/System-Design/blob/master/Cache/README.md "时髦一点，选择dubbo，微服务让团队开发耦合度没有那么高，各自关心各自的模块，都以服务方式发布出去。传统一点用springmvc+restful，在我看来，对于并发不高的系统，没有必要用dubbo。缓存的选择，涉及到文件缓存、数据库缓存，可以用memcached、ehcache、redis")
   * 配置中心
   * 服务中心   
     * 服务名字系统
     * 服务总线系统
   * 分布式消息
     * 消息队列
       * RocketMQ
       * Kafka
       * ActiveMQ
     * 任务队列
     * 背压机制  
   * 分布式缓存
     * [缓存系统](https://github.com/stevenli91748/System-Design/blob/master/Cache/README.md)
       * [Client caching]
       * [HTTP  Caching]  
         * [HTTP----HTTP缓存机制](https://juejin.im/post/5a1d4e546fb9a0450f21af23)
       * [CDN caching]
       * [Web server caching ]
       * [Database caching]
       * [Application caching]
       * [Caching at database query level]
       * [Caching at object level]
       * [When to update the cache]
         * [Cache aside]
         * [Write through]
         * [Write behind]
         * [Refresh ahead]
   * [分布式session](https://github.com/stevenli91748/System-Design/blob/master/Session/README.md)
   * [分布式服务](https://github.com/stevenli91748/Distributed-System)
     * [Microservice](https://github.com/stevenli91748/MicroService)
     * [Service Discovery]
   

   
### 2.4. 存储层架构
   * 分布式文件
      * 小文件存储
        * HBase
        * Hadoop
        * Hypertable
        * FastDFS
        * TFS(taobao)
        * JFS(JD)
        * Haystack(facebook)
      * 大文件存储
        * Hadoop
        * HBase
        * Storm
        * Hive
   * [关系数据库](https://github.com/stevenli91748/Database/blob/master/README.md)
     * [Master slave replication]
     * [Master master replication]
     * [Federation]
     * [Sharding]
     * [Denormalization]
     * [SQL tuning]
   * 非关系数据库
     * [key-value store]
     * [Document store]
     * [Wide column store ]
     * [Graph database]
   * 数据同步
   
### 2.5 开发层架构
   * 开发框架
     * JAVA
       * SSH
       * SSM
       * SpringMVC
       * SpringBoot
       * SpringCloud
   * WEB服务器
     * Tomcat
     * Nginx
     * JBoss
     * Resin
   * 容器
     * Docker
     
### 2.6 网络层架构
   * 负载均衡
     * [DNS (Domain Name System)---用于实现地理级别的负载均衡  ](https://github.com/stevenli91748/System-Design/blob/master/DNS/README.md)
     * Nginx & LVS & F5----用于同一地点内机器级别的负载均衡
     * [CDN (Content Delivery Network)](https://github.com/stevenli91748/System-Design/blob/master/CDN/README.md)
       * [Push CDNs]
       * [Pull CDNs]
     * 分布式存储
     * 全局负载均衡
     * 网络重定向
     * 流量控制
   * [网络通信](https://github.com/stevenli91748/Network/blob/master/README.md)
   * 多机房
   * 多中心

### 2.7 后台架构
   * 运维平台架构
     * 配置
     * 部署
     * 监控
     * 应急
   * 测试平台架构
     * 单元测试
     * 集成测试
     * 接口测试
     * 性能测试
   * 数据平台架构
     * 数据管理
     * 数据分析
     * 数据应用
       * 数据采集与监控架构
         * 浏览器数据采集
         * 服务器业务数据采集
         * 服务器性能数据采集
         * 系统监控
         * 系统报警

   * 管理平台架构
     * 权限管理
       * 身份认证
       * 权限控制
     
 ---  

# 3. 代码

  * []()
  * []()
  * []()
  * []()  

---

# 4. 部署

---

# 5. 服务器

---

# 6. 运维

---

# 7. 调优

---

# 参考书籍
 * 从零开始学架构：照着做，你也能成为架构师.pdf
 * 从零开始学架构--系列文集.pdf
 * 人人都是架构师  分布式系统架构落地与瓶颈突破.pdf
 * 大型网站技术核心原理与案例分析.pdf
 * 大型网站技术架构演进与性能优化.pdf
 * 软件架构设计：大型网站技术架构与业务架构融合之道.pdf
 * 架构解密.从分布式到微服务.pdf
 * 亿级流量网站架构核心技术+跟开涛学搭建高可用高并发系统.pdf
 * 架构宝典架构.pdf
 * 聊聊架构.pdf
 * 架构真经-互联网技术架构的设计原则.pdf
 
 * [大型网站架构系列：20本技术书籍推荐](https://blog.csdn.net/zdy0_2004/article/details/50513152)

# 有用的参考
 * [从新手到架构师，一篇就够：从100到1000万高并发的架构演进之路](http://www.52im.net/thread-2665-1-1.html)
 * [关于一个大型web系统架构设计和技术选型的讨论摘录](https://blog.csdn.net/zhang_yingliang/article/details/50585343)
 * [大型web系统架构详解](https://blog.csdn.net/zhulongxi/article/details/73549028)
 * [服务端-高并发高可用设计原则/分布式架构演进过程](https://blog.csdn.net/hemin1003/article/details/95163321)
 * [打造互联网企业架构相关技术（实战干货）](https://blog.csdn.net/qq_27384769/article/details/79439922)
 * [如何规划学习步骤](https://blog.csdn.net/weixin_44135121/article/details/93226590)
 * [近二十年技术发展：从集中式架构到云原生架构](https://blog.csdn.net/weixin_44326589/article/details/93894615)
 * [分享一篇牛人的工作总结,让大家感受一下什么叫优秀的架构师](https://blog.csdn.net/smooth00/article/details/92803798)
 * [一个程序员如何能成为一名资深阿里P7架构师？](https://yq.aliyun.com/articles/660334)
 * [IT技术精华网关注搜索、分布式系统、云计算、系统架构设计、性能调优、Web开发、数据挖掘、推荐系统](http://www.chepoo.com)
 * [你是主流架构师吗](http://www.10tiao.com/html/158/201903/2649826500/1.html)
 * [程序员一般喜欢浏览哪些网站呢？](https://www.zhihu.com/question/283272958/answer/598956527?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
  * [最牛Java架构师进阶路线](https://blog.csdn.net/hang1995/article/details/79371268)
  * [石杉的架构笔记](https://juejin.im/user/5be0588ae51d452b0255727d)
  * [软件开发工作过程中的一些总结](http://www.youmeek.com/java-sofaware-engineer/)
  * [架构设计和技术选型的思路总结](https://blog.csdn.net/yl2isoft/article/details/53217833)
  * [后台服务程序框架技术选型方案](https://blog.csdn.net/coloriy/article/details/66969756)
  * [组件化、模块化、集中式、分布式、服务化、面向服务的架构、微服务架构](https://blog.csdn.net/AlbenXie/article/details/73478162)
  * [web前端技术框架选型参考](https://blog.csdn.net/aaa333qwe/article/details/78416211)
  * [几种后端开发技术的选型调研](https://blog.csdn.net/dipolar/article/details/51804192)
  * [后台服务程序框架技术选型方案](https://blog.csdn.net/coloriy/article/details/66969756)
  * [传统架构到分布式架构](https://blog.csdn.net/samjustin1/article/details/81073845)
  * [个人开发web应用，从需求设计，界面设计，数据库设计，API设计等，好的开发流程是怎么样的？](https://www.zhihu.com/question/24976128)
  * [一个比较不错的大型分布式网站架构技术总结，可做参考](https://blog.csdn.net/hjm4702192/article/details/79612611)
  * [大型分布式网站架构实战项目分析](https://blog.csdn.net/yunzhaji3762/article/details/80113693)
  * [大型网站架构演化](https://www.jianshu.com/p/526df44a11f1)
  * [技术方案设计](https://blog.csdn.net/my201110lc/article/details/82229611#_Toc512435238)
  * [架构师之路-创业互联网公司如何搭建自己的技术架构](https://blog.csdn.net/zhaorui2017/article/details/78133686)
 ### 大型网站架构 
  * [深入解析java应用程序的一般架构（好文）](https://blog.csdn.net/hliq5399/article/details/51584622)
  * [LMAX架构](http://ifeve.com/lmax/)
  * [从 0 到 1，Java Web 网站架构搭建的技术演进](https://blog.csdn.net/qq_40267706/article/details/78628352)
  * [1千用户与1千万用户的网站系统架构区别？](https://blog.csdn.net/zqftisson/article/details/51777042)
  * [大型分布式电商系统架构是如何从0开始演进的？](https://blog.csdn.net/jianai0602/article/details/80346837)
  * [电商系统学习笔记之一系统架构](https://blog.csdn.net/hanruikai/article/details/79928211)
  * [百万级别网站架构思路](https://blog.csdn.net/ahjxhy2010/article/details/79854980)
  * [大型电商网站千万级别架构案例和技术架构【推荐】](https://blog.csdn.net/jianai0602/article/details/80346837)
  * [结合实例谈项目架构设计](https://blog.csdn.net/javayujiafeng/article/details/79086710)
  * [吃透这套架构演化图，从零搭建Web网站也不难！](https://mp.weixin.qq.com/s?__biz=MzI4NTA1MDEwNg==&mid=2650763749&idx=1&sn=74b4fea08061fde4e5cee4dca47246ce&chksm=f3f9c470c48e4d665e15ee6e156ca2a42d18a71cacefd0d07acba4e85259b65b34631a641628&scene=21#wechat_redirect)
  * [3分钟读懂何为分布式、微服务和集群](https://juejin.im/entry/59fa91225188255851320783)
  * [消息中间件如何实现每秒几十万的高并发写入？](https://juejin.im/post/5c7bd09b6fb9a049ba424c15)
  * [线上服务宕机时，如何保证数据100%不丢失](https://juejin.im/post/5c190f02518825046c2f6a5c)
  * [阿里 P9 级面试官是如何 360° 无死角考察候选人的？](https://blog.csdn.net/csdnnews/article/details/89702195)
  * [设计扛住千万级流量架构](https://blog.csdn.net/qq_35394891/article/details/80992999)
  
### 亿级流量系统架构

* [亿级流量系统架构之如何支撑百亿级数据的存储与计算](https://juejin.im/post/5bfab59fe51d4551584c7bcf)
* [亿级流量系统架构之如何设计高容错分布式计算系统](https://juejin.im/post/5bfbeeb9f265da61407e9679)
* [亿级流量系统架构之如何设计承载百亿流量的高性能架构](https://juejin.im/post/5bfd2df1e51d4574b133dd3a)
* [亿级流量系统架构之如何设计每秒十万查询的高并发架构](https://juejin.im/post/5bfe771251882509a7681b3a)
* [亿级流量系统架构之如何设计全链路99.99%高可用架构](https://juejin.im/post/5bffab686fb9a04a102f0022)
* [亿级流量系统架构之如何在上万并发场景下设计可扩展架构（上）](https://juejin.im/post/5c221654e51d45229f76e647)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（中）](https://juejin.im/post/5c3362dcf265da6134389321)
* [亿级流量系统架构之如何在上万并发场景下设计可扩展架构（下）](https://juejin.im/post/5c242848f265da615a41de2c)
* [亿级流量架构第二弹：你的系统真的无懈可击吗](https://juejin.im/post/5c2e07df6fb9a049c30b5f28)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（上）](https://juejin.im/post/5c321143f265da615304eb6b)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（中）](https://juejin.im/post/5c3362dcf265da6134389321)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（下）](https://juejin.im/post/5c34a74be51d4557db5a03fc)


### 项目经验
 * [一个经典面试题：如何保证缓存与数据库的双写一致性？](https://blog.csdn.net/devcloud/article/details/90440921)


# 项目实战

<a href="https://ibb.co/yfFwVxw"><img src="https://i.ibb.co/znVyNty/along.jpg" alt="along" border="0"></a>

* [项目实战1—LNMP的搭建、nginx的ssl加密、身份验证的实现](https://www.cnblogs.com/along21/p/7822228.html)
* [项目详解2—LVS负载均衡详解](https://www.cnblogs.com/along21/p/7784394.html)
* [项目实战2—实现基于LVS负载均衡集群的电商网站架构](https://www.cnblogs.com/along21/p/7833261.html)
* [项目实战2.1—nginx 反向代理负载均衡、动静分离和缓存的实现](https://www.cnblogs.com/along21/p/7842729.html)
* [项目实战3—实现基于Keepalived+LVS的高可用集群网站架构](https://www.cnblogs.com/along21/p/7841132.html)
* [项目实战4—HAProxy实现高级负载均衡实战和ACL控制](https://www.cnblogs.com/along21/p/7873998.html)
* [项目详解4—haproxy 反向代理负载均衡](https://www.cnblogs.com/along21/p/7899771.html)
* [项目实战5—企业级缓存系统varnish应用与实战](https://www.cnblogs.com/along21/p/7911628.html)
* [项目实战6—Mysql实现企业级日志管理、备份与恢复实战](https://www.cnblogs.com/along21/p/8005775.html)
* [项目实战7—Mysql实现企业级数据库主从复制架构实战](https://www.cnblogs.com/along21/p/8011596.html)
* [项目实战8—tomcat企业级Web应用服务器配置与会话保持](https://www.cnblogs.com/along21/p/8024719.html)
* [项目实战8.1-Linux下Tomcat开启查看GC信息](https://www.cnblogs.com/along21/p/9177578.html)
* [项目实战9—企业级分布式存储应用与实战MogileFS、FastDFS](https://www.cnblogs.com/along21/p/7911676.html)
* [项目实战10.1—企业级自动化运维工具应用实战-ansible](https://www.cnblogs.com/along21/p/8241542.html)
* [项目实战10.2--企业级自动化运维工具---puppet详解](https://www.cnblogs.com/along21/p/10369858.html)
* []()
* [项目实战11—企业级nosql数据库应用与实战-redis的主从和集群](https://www.cnblogs.com/along21/p/8027206.html)
* [项目实战12.1—企业级监控工具应用实战-zabbix安装与基础操作](https://www.cnblogs.com/along21/p/8118609.html)
* [项目实战12.2—企业级监控工具应用实战-zabbix操作进阶](https://www.cnblogs.com/along21/p/8119088.html)
* [项目实战13—企业级虚拟化Virtualization - KVM技术](https://www.cnblogs.com/along21/p/8116509.html)
* [项目实战14.1—ELK 企业内部日志分析系统](https://www.cnblogs.com/along21/p/8509123.html)
* [项目实战14.2--ELK 经典用法—企业自定义日志收集切割和mysql模块](https://www.cnblogs.com/along21/p/8513420.html)
* [项目实战14.3--ELK重难点总结和整体优化配置](https://www.cnblogs.com/along21/p/8613115.html)
* [项目实战15.1—企业级堡垒机 jumpserver一步一步搭建](https://www.cnblogs.com/along21/p/8795907.html)
* [项目实战15.2—企业级堡垒机 jumpserver快速入门](https://www.cnblogs.com/along21/p/8965968.html)
* [项目实战16.1--Jenkins持续集成01—Jenkins服务搭建和部署](https://www.cnblogs.com/along21/p/9724036.html)
* [项目实战16.2--Jenkins+Maven+Gitlab+Tomcat 自动化构建打包、部署](https://www.cnblogs.com/along21/p/10172855.html)
* [项目实战17--超详细“零”基础kafka入门篇](https://www.cnblogs.com/along21/p/10278100.html)
* [项目实战18--Hadoop+Hbase分布式集群架构“完全篇”](https://www.cnblogs.com/along21/p/10496468.html)













