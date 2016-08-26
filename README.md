云课堂ID：北风127
登陆邮箱：zhongxue_dai@126.com

服务端微专业示例工程
=================================
## 总体说明
总体以云课堂用户中心页面为参考，各课程根据需要添加必要的使用场景。后端目前已按标准工程结构组织，各课程根据内容添加必要的实现（如模板使用，数据库使用等）

## 页面说明
* 登录页：/index.html
* 用户名：server，密码：123，跳转到用户中心/user页面；

## 实现说明
* /user页面目前由后端servlet直接输出html生成；
* dao目前未连接数据库，用户信息代码中写死；

## 2016-08-26  Add by Gary
## test Servlet/ServletConfig
    ﻿    ﻿1.使用$CATALINA_HOME/bin/catalina.sh run 开启tomcat
    ﻿    ﻿2.在eclipse项目右键 run as-> run application -> maven   mvn tomcat7:redeploy   注意看deploy是FAIL还是OK。
    ﻿    ﻿3.开shell用curl测试。
     ﻿	4.出错的地方：init-param中 param-value标签写错。

## 2016-08026  Add by Gary
## test Servlet/ServletContext set&&getAttribute
出现的问题：
        1.servlet-class 包名写错，提示ClassNotFound
        2.ServletContext get 的值是int，不能强转为String，加个toString()
    ﻿    ﻿3.提示：HTTP Status 405 - HTTP method GET is not supported by this URL</h1><HR size="1" noshade="noshade"><p><b>type</b> Status report</p><p><b>message</b> <u>HTTP method GET is not supported by this URL</u></p><p><b>description</b> <u>The specified HTTP method is not allowed for the requested resource.
    ﻿    ﻿   需要在重写的service()和doGet() 中取消super()的调用。
        这错误报的简直太低级了！！！