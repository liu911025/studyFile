```java
package com.tempus.common.utils;

import com.tempus.baseservice.service.international.InRefundApprefManager;
import org.apache.http.HttpEntity;
import org.apache.http.HttpResponse;
import org.apache.http.HttpStatus;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.CloseableHttpResponse;
import org.apache.http.client.methods.HttpGet;
import org.apache.http.client.methods.HttpPost;
import org.apache.http.entity.StringEntity;
import org.apache.http.impl.client.CloseableHttpClient;
import org.apache.http.impl.client.HttpClients;
import org.apache.http.util.EntityUtils;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.stereotype.Component;

import java.io.IOException;
import java.nio.charset.Charset;

/**
 *  HttpClientUntil
 */
public class HttpClientUntil {

    private static Logger logger = LoggerFactory.getLogger(HttpClientUntil.class);

    /**
     *  post 提交
     * @param url
     * @param paramJson
     * @return
     */
    public static String post(String url, String paramJson) {
        logger.info("httpClient -- POST请求地址:{" + url + "},请求参数为:" + paramJson);
        CloseableHttpClient httpClient = HttpClients.createDefault();
        try {
            HttpPost httpPost = new HttpPost(url);

            httpPost.setHeader("Content-type", "application/json");
            StringEntity entity = new StringEntity(paramJson, Charset.forName("UTF-8"));
            entity.setContentEncoding("UTF-8");
            // 发送Json格式的数据请求
            entity.setContentType("application/json");
            httpPost.setEntity(entity);
            HttpResponse response = httpClient.execute(httpPost);
            int statusCode = response.getStatusLine().getStatusCode();
            logger.info("请求状态码:" + statusCode);
            if (null != response && HttpStatus.SC_OK == statusCode) {
                HttpEntity result = response.getEntity();
                String resultStr = EntityUtils.toString(result, "utf-8");
                logger.info("httpClient请求结果:" + resultStr);
                return resultStr;
            }
        } catch (IOException e) {
            logger.info("HttpClientUntil -- POST提交异常");
            e.printStackTrace();
        }finally {
            try {
                httpClient.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
        return null;
    }

    /**
     *  get 提交
     * @param url
     * @return
     */
    public static String get(String url) {
        logger.info("httpClient -- GET请求地址:{" + url + "}");
        CloseableHttpClient httpClient = HttpClients.createDefault();
        try {
            HttpGet httpGet = new HttpGet(url);
            CloseableHttpResponse response = httpClient.execute(httpGet);
            if (null != response && response.getStatusLine().getStatusCode() == HttpStatus.SC_OK) {
                HttpEntity entity = response.getEntity();
                String result = EntityUtils.toString(entity, "utf-8");
                logger.info("httpClient -- GET请求结果: " + result);
                return result;
            }
        } catch (IOException e) {
            logger.info("HttpClientUntil -- GET提交异常");
            e.printStackTrace();
        }finally {
            try {
                httpClient.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
        return null;
    }
}

```

