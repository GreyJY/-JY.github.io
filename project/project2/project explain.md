这个就是单纯的一个Java编写出来的一个后端小项目，纯Java手搓，小型客户端控制台的机器人
该项目底层逻辑框架
没有 HTML、CSS、JavaScript，因此没有真正的前端。
没有 Spring Boot、Controller、数据库，也不是 Web 后端服务。
Java 程序通过 OkHttp 调用第三方机器人 API。
Fastjson 负责把 Java 对象转成 JSON，并解析接口响应。
历史运行记录显示请求曾成功：控制台打印了一条上海天气信息，进程以退出码 0 结束。
页面至少目前无需登录、凭链接即可看到并操作源码，其中还包含明文 API 凭据，安全风险较高。

Maven：这个项目怎么依赖、编译、测试、打包
Git：这个项目的文件修改历史是什么

但是从中学到了Maven的数据管理（自动帮你生成一定项目框架）以及idea的自动创立文件，还有setter，getter方法的作用（为了访问私有数据类用的，可以直接用idea帮你生成）
j1_9_1_20_cs
├── .idea（idea自己生成）
├── src（自己写的）
│   └── main
│       └── java
│           └── com.youkeda
│               ├── model（数据的模型，用来规范放到json里面数据的格式）
│               ├── service（放业务逻辑代码）
│               └── Application（项目启动的入口）
├── target（maven编译后自己产生的目录）
└── pom.xml（管理依赖的库，一般maven管理自动生成）
