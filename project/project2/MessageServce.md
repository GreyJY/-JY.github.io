package com.youkeda.service;

/**
 * 对话内容
 *
 * @author joe
 * @date 2019-07-06
 */
public class MessageService {

    public RobotService robot = new RobotService();

    /**
     * 发消息
     *
     * @param message
     */
    public String send(String message) {
        String reply = robot.reply(message);
        return reply;
    }

}
