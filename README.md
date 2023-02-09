
<p align="center">
	<img alt="logo" src="https://oscimg.oschina.net/oscnet/up-dd77653d7c9f197dd9d93684f3c8dcfbab6.png">
</p>
<h1 align="center" style="margin: 30px 0 30px; font-weight: bold;">SDNU v2.0</h1>
<h4 align="center">基于SpringBoot+React+Postgresql前后端分离的数据库实训平台</h4>
<p align="center">
	<a href="https://gitee.com/feixiangdexiaozhidan/mytest"><img src="https://img.shields.io/badge/sdnu-v2.0-brightgreen.svg"></a>
	<a href="https://gitee.com/feixiangdexiaozhidan/mytest/blob/master/LICENSE"><img src="https://img.shields.io/github/license/mashape/apistatus.svg"></a>

</p>


## 项目说明
* sdnu平台是一套全部开源的教学平台，毫无保留给个人及企业免费使用。
* sdnu项目是一个轻量级的，前后端分离的Java教学平台，可以支撑起数据库系列课程及其他课程的教学。教师端在平台进行备课、教学、出题、发布作业、批改作业、查看学习进度等，学生端可在此平台进行上课学习、完成作业等丰富的课程资源，提升课程质量和教学效率。让整个教学过程进行可持续的改进和优化，最终打造成一个一站式教学资源的整合平台。
* 前端采用React、antd-pro、ts
* 后端采用Spring Boot、Mybatis-Plus、Jwt
* 权限认证使用Jwt安全可控
* 支持Postgresql数据库
* 前端地址:
* 演示地址: http://118.190.151.85:59005/user/login（账号密码:admin/admin）
* 操作手册：https://feixiangdexiaozhidan.github.io

## 内置功能
* 用户管理: 完成平台用户的配置管理
* 角色管理: 角色权限分配
* 模块管理: 功能模块显示查询及各模块显示设置
* 个人设置: 设置个人信息，修改个人密码
* 意见反馈: 搜集用户意见
* 我的课程: 当前用户下的课程
* 课程模板: 课程专家和教师用户个人的课程模板，用于说明本学期开设的课程
* 班级: 当前教师角色下所有的班级信息，新建班级
* 介绍: 进入课程后的课程信息
* 章节: 用于教师备课、授课、编辑课程内容、统计学生学习进度，学生角色查看学生任务、个人学习进度统计、课程学习
* 知识: 该课程下知识点展示
* 题库: 用于教师端出题
* 作业: 用于教师端新建作业、发布作业、批改作业、查看学生作业情况


## 项目结构
```
─src
  │  └─main
  │      ├─java
  │      │  └─com
  │      │      └─highgo
  │      │          └─edu
  │      │              ├─api                 restful接口
  │      │              ├─catalogue           章节目录                  
  │      │              │  ├─domain
  │      │              │  │  └─entity
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─common               公共资源
  │      │              │  ├─advice
  │      │              │  ├─annotation
  │      │              │  ├─batchOperation
  │      │              │  ├─bean
  │      │              │  ├─constant
  │      │              │  ├─entity
  │      │              │  ├─events
  │      │              │  ├─exception
  │      │              │  │  ├─assertion
  │      │              │  │  ├─enums
  │      │              │  │  ├─handler
  │      │              │  │  └─i18n
  │      │              │  ├─Interval
  │      │              │  ├─listener
  │      │              │  ├─mapper
  │      │              │  ├─service
  │      │              │  │  └─impl
  │      │              │  └─utils
  │      │              ├─contents                章节内容
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─course                  课程相关
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─exercise                习题相关
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─feedback                 意见反馈相关
  │      │              │  ├─mapper
  │      │              │  ├─model
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─homework                 作业相关
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─manage
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─homeworkmodel            作业模板相关
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─login                     登录相关
  │      │              │  ├─mapper
  │      │              │  ├─model
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─migration                 历史数据迁移相关（忽略）
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─process                   学生学习进度相关
  │      │              │  ├─domain
  │      │              │  │  └─entity
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─progress                  学生练习相关（暂时不用）
  │      │              │  ├─mapper
  │      │              │  ├─model
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─resources                  资源相关
  │      │              │  ├─domain
  │      │              │  │  └─entity
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─sclass                      班级相关
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─statistics                  章节统计相关
  │      │              │  ├─domain
  │      │              │  │  └─model
  │      │              │  └─service
  │      │              │      └─impl
  │      │              ├─system                      系统设置相关
  │      │              │  ├─domain
  │      │              │  │  ├─entity
  │      │              │  │  └─model
  │      │              │  ├─mapper
  │      │              │  └─service
  │      │              │      └─impl
  │      ├─resources                                   配置信息
  │      └─webapp                                      静态资源信息
```
## 技术选型 
* 核心框架：Spring Boot 2.5.1
* 安全框架：Jwt 3.15.0
* 持久层框架：MyBatis-Plus 3.4.0
* 数据库连接池：HikariCP 4.0.3
* 日志管理：Logback
* 页面交互：React 17.0.0  
## 软件需求
* JDK1.8
* Maven3.0+
* PostgreSQL 9.4+
## 本地部署
### 步骤
* 通过git下载源码: git clone + 项目git地址
* idea、eclipse需安装lombok插件，不然会提示找不到entity的get set方法
* /lib目录下的两个jar包放到相应的maven仓库com.aspose包下
* 安装Postgresql数据库后，新建数据库，编码模式UTF-8
* 在新建数据库默认publish模式下执行resources/init.sql文件，初始化数据
* 修改resources/application.properties,配置个人数据库信息
* maven clean 、 package
* 配置tomcat并部署项目sdnu-edu-api.war，名称为/sdnu-edu-api
* 启动项目
### 访问
* 部署启动前端项目，前端项目地址：https://gitee.com/XXX
* 账号密码：admin/admin, js/js
## 如何贡献
* 提交一个问题或者功能, 请在提交前进行验证.
* 审阅 网站 ，对于任何拼写错误或者内容建议，请创建 pull requests
