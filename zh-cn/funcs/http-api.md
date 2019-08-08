
## http.downloadFile(String remoteUrl, File file, int timeout)
* @description 下载远程文件到本地,支持断点续传
* @param remoteUrl 远程文件URL
* @param file      要保存到本地的文件对象
* @param timeout   下载超时，单位是毫秒
* @return true 代表成功 false代表失败

> ```java
> boolean downloaded = http.downloadFile("http://baidu.com/a.apk",new File("/sdcard/a.apk"),30*1000));
> ```



## http.downloadFile(String remoteUrl, String file)
* @description 下载远程文件到本地,支持断点续传，默认超时时间为30秒
* @param remoteUrl 远程文件URL
* @param file      要保存到本地的文件对象
* @return true 代表成功 false代表失败

> ```java
> boolean downloaded = http.downloadFile("http://baidu.com/a.apk","/sdcard/a.apk");
> ```


## http.httpGet(String url, int timeout)
* @description Http GET 请求
* @param url 请求的URL
* @param timeout 超时时间 单位毫秒
* @return 字符串 请求后返回的字符串

> ```java
> String data = http.httpGet("http://baidu.com/",30*1000);
> ```


## http.httpGet(String url,HashMap<String, String> params, int timeout)
* @description Http GET 请求
* @param url 请求的URL
* @param params  参数Map表
* @param timeout 超时时间 单位毫秒
* @return 字符串 请求后返回的字符串

> ```java
> HashMap<String,String> params= new HashMap<>();
> params.put("a","test");
> String data = http.httpGet("http://baidu.com/",params,30*1000);
> ```



## http.httpPost(String url,HashMap<String, String> params, int timeout)
* @description Http Post 请求
* @param url 请求的URL
* @param params  参数Map表
* @param timeout 超时时间 单位毫秒
* @return 字符串 请求后返回的字符串

> ```java
> HashMap<String,String> params= new HashMap<>();
> params.put("a","test");
> String data = http.httpPost("http://baidu.com/",params,30*1000);
> ```

