该项目是用springboot+vaadin框架一起做的TODO表单

springboot在这主要是在Application做运行文件，启动类
springboot启动类的作用是启动spring容器
启动服务器
    +
加载你的Java代码 
    +
启动网页
的作用

而这个网页的前端是vaadin框架自动帮你生成了前端

网站的后端在for(User user : Reg.users){

   if(
    user.getUserName().equals(userName)
    &&
    user.getPassword().equals(password)
    )
    longinview里面
  输入账号密码
       |
   LoginForm
       |
  LoginEvent
       |
  onLogin()
       |
读取Reg.users
       |
判断账号密码

登陆数据在public void onLogin(AbstractLogin.LoginEvent event){

  String userName = event.getUserName();

   String password = event.getPassword();
这里传递数据，用户把数据填入，然后传递到后端

数据库用public static List<User> users = new ArrayList<>();这个列表容器代替存储这个User的数据，转到json文件里面自动生成有序的数据

想要查看用户数据就取断点debug来看

这个项目的项目框架是        正常公司项目的项目框架                                         
     |                             |
  Vaadin                           |
    |                              |
  Java代码                         |
    |                              |
  JSON文件                         | 
                                 Vue
                                  |
                              HTTP请求
                                  |
                       Spring Boot Controller
                                  |
                               Service
                                  |
                                Mapper
                                  |
                                MySQL
我的项目是Java全栈            公司项目是vue+springboot      
