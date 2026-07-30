相当于用 OkHttpClient client = new OkHttpClient();这个来方法来调用ai的api来实现这个机器人的交互

package com.youkeda.service;

import com.alibaba.fastjson.JSON;
import com.alibaba.fastjson.JSONObject;
import com.youkeda.model.RobotMessageRequest;
import okhttp3.*;

import java.io.IOException;

/**
 * RobotService
 */
public class RobotService {

    OkHttpClient client = new OkHttpClient();


    String post(String json) throws IOException {

    RequestBody body = RequestBody.create(MediaType.get("application/json; charset=utf-8"), json);
        Request request = new Request.Builder().url("http://openapi.tuling123.com/openapi/api/v2").post(body).build();

   try (Response response = client.newCall(request).execute()) {
            JSONObject object = JSON.parseObject(response.body().string());
            return object.getJSONArray("results").getJSONObject(0).getJSONObject("values").getString("text");
        }
    }

    public String reply(String input) {

    RobotMessageRequest request = new RobotMessageRequest();
    RobotMessageRequest.InputText inputText = new RobotMessageRequest.InputText();
        inputText.setText(input);
        RobotMessageRequest.Perception perception = new RobotMessageRequest.Perception();
        perception.setInputText(inputText);
        request.setPerception(perception);

   String json = JSON.toJSONString(request);
        String msg = null;
        try {
            msg = post(json);
        } catch (IOException e) {
            e.printStackTrace();
        }
        return msg;
    }

}
