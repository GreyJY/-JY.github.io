关于spring框架的内容
Spring Boot：启动和自动配置（启动类最常用到）
Spring IOC：创建对象、管理对象、依赖注入（自动创建对象，放入ioc容器里面）
Spring MVC：接收 HTTP 请求（连接前后端，后端有什么想法都可以返回到前端，前端有什么信息也会返回后端）
Spring Data JPA：操作数据库（跟数据库连接关系）
Spring AOP：统一记录日志
Spring Transaction：事务与回滚
Spring Validation：参数校验
Spring Security：登录验证
Spring Actuator：观察 Spring 容器
8/4
浏览器
 |
 | 请求 /songlist
 ↓
Controller
 |
 | 调用
 ↓
Service
 |
 | 查询
 ↓
数据库返回 SongList对象
 |
 ↓
Model保存数据
 |
 ↓
Thymeleaf读取Model
 |
 ↓
生成最终HTML
 |
 ↓
浏览器显示
