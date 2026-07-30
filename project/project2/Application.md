这里依旧是程序启动入口只不过这集没有用spring boot，直接单纯靠Java单体代码组成，不同类之间去引用的

package com.youkeda;

import com.youkeda.service.MessageService;

/**
 * Application
 */
public class Application {

    public static MessageService messageService = new MessageService();

    public static void main(String[] args) {
        String reply = messageService.send("今天天气怎么样");
        System.out.println(reply);

   if (reply.indexOf("查询哪个城市") != -1) {
            reply = messageService.send("杭州");
            System.out.println(reply);
        }

   //强制退出程序
        System.exit(0);
    }

}
