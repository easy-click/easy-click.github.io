?> 该文档主要列出了重要功能的函数使用，其他更明细函数请查看javadoc, [下载javadoc](/zh-cn/api-docs?id=javadoc-下载和使用)

## 主任务和子任务
 - 主任务和子任务无本质区别，只是逻辑上区分而已
 - 主任务继承com.gibb.auto.open.BaseCaseMain
 - 子任务继承com.gibb.auto.open.testcase.SubTestCase
 - 子任务和主任务都包含了相同的功能函数，只要继承即可拥有以下能力:
    - device 变量: 设备相关的API封装
    - event 变量: Ui事件相关的API封装   
    - file 变量: 文件操作相关的API封装
    - http 变量: HTTP网络操作相关的封装
    - image 变量: 图像相关的API封装
    - shell 变量: Shell命令操作相关的Api封装

## 设备信息函数-device
###  device.getIMEI()
* @description 获取手机的IMEI
* @return 字符串

> ```java
> String imei = device.getImei();
> ``` 

###  device.getScreenWidth()
* @description 取得屏幕宽度
* @return 整型

> ```java
> int width = device.getScreenWidth();
> ``` 



###  device.getScreenHeight()
* @description 取得屏幕高度
* @return 整型

> ```java
> int height = device.getScreenHeight();
> ``` 


###  device.getAndroidId()
* @description 取得Android ID
* @return 字符串

> ```java
> String androidId = device.getAndroidId();
> ``` 


###  device.getBrand()
* @description 取得手机品牌
* @return 字符串

> ```java
> String brand = device.getBrand();
> ``` 


###  device.getModel()
* @description 取得手机机型
* @return 字符串

> ```java
> String model = device.getModel();
> ``` 


###  device.getImsi()
* @description 取得手机卡号
* @return 字符串

> ```java
> String imsi = device.getImsi();
> ```


###  device.getSerial()
* @description 取得手机串号
* @return 字符串

> ```java
> String serial = device.getSerial();
> ``` 


###  device.getSdkInt()
* @description 取得手机SDK 版本号，例如 23
* @return 字符串

> ```java
> int sdkInt = device.getSdkInt();
> ```

###  device.getOSVersion()
* @description 取得手机版本号,例如 6.0等字符串
* @return 字符串

> ```java
> String osVersion = device.getOSVersion();
> ```





## 文件操作函数
### file.readFile(String path)
* @description 将文件读取为字符串
* @param path 文件路径
* @return 字符串

> ```java
> String data = file.readFile("/sdcard/test.txt");
> ```


### file.writeFile(String data, String path)
* @description 将字符串存储到文件中
* @param data 字符串 数据
* @param path 文件路径

> ```java
> String data="Test";
> file.writeFile(data,"/sdcard/test.txt");
> ```


### file.create(String path)
* @description 创建一个文件或者文件夹
* @param path 文件或者文件夹路径
* @return 布尔型 true 代表创建成功

> ```java
> boolean create=file.create("/sdcard/test.txt");
> ```        

### file.readAssets(String path)
* @description 从APK的assets文件夹中读取数据为字符串
* @param path assets文件夹中的文件路径，例如 data/a.txt
* @return 字符串

> ```java
> String data=file.readAssets("data/test.txt");
> ```


### file.deleteAllFile(String path)
* @description 删除所有文件或者文件夹
* @param path 文件或者文件路径

> ```java
> file.deleteAllFile("data/test.txt");
> ```

## Http网络函数

### downloadFile(String remoteUrl, File file, int timeout)
* @description 下载远程文件到本地,支持断点续传
* @param remoteUrl 远程文件URL
* @param file      要保存到本地的文件对象
* @param timeout   下载超时，单位是毫秒
* @return true 代表成功 false代表失败

> ```java
> boolean downloaded = http.downloadFile("http://baidu.com/a.apk",new File("/sdcard/a.apk"),30*1000));
> ```



### downloadFile(String remoteUrl, String file)
* @description 下载远程文件到本地,支持断点续传，默认超时时间为30秒
* @param remoteUrl 远程文件URL
* @param file      要保存到本地的文件对象
* @return true 代表成功 false代表失败

> ```java
> boolean downloaded = http.downloadFile("http://baidu.com/a.apk","/sdcard/a.apk");
> ```


### httpGet(String url, int timeout)
* @description Http GET 请求
* @param url 请求的URL
* @param timeout 超时时间 单位毫秒
* @return 字符串 请求后返回的字符串

> ```java
> String data = http.httpGet("http://baidu.com/",30*1000);
> ```


### httpGet(String url,HashMap<String, String> params, int timeout)
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



### httpPost(String url,HashMap<String, String> params, int timeout)
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




## Shell命令函数

### shell.installApp(String path)
* @description 安装 apk
* @param path 文件路径
* @return true 代表安装成功，false 代表安装失败

> ```java
> boolean result = shell.installApp("/sdcard/app.apk");
> ```


### shell.uninstallApp(String packageName)
* @description 卸载应用程序
* @param packageName 应用程序的包名
* @return true 代表卸载成功，false 代表卸载失败

> ```java
> boolean result = shell.uninstallApp("com.ss.android.article.news");
> ```


### shell.openApp(String packageName)
* @description 打开APP
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败

> ```java
> boolean result = shell.openApp("com.ss.android.article.news");
> ```

### shell.stopApp(String packageName)
* @description 停止正在执行的应用
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败

> ```java
> boolean result = shell.stopApp("com.ss.android.article.news");
> ```



### shell.isAppExist(String packageName)
* @description App是否已经安装
* @param packageName 应用程序的包名
* @return true 代表已经安装，false代表未安装

> ```java
> boolean result = shell.isAppExist("com.ss.android.article.news");
> ```

### shell.getAppVersionCode(String packageName)
* @description 取得已安装的程序的版本整型标示
* @param packageName 应用程序的包名
* @return 整型

> ```java
> int versionCode = shell.getAppVersionCode("com.ss.android.article.news");
> ```


### shell.getAppVersionCode(String packageName)
* @description 取得已安装的程序的版本字符串标示
* @param packageName 应用程序的包名
* @return 字符串，例如 1.0.0

> ```java
> String versionName = shell.getAppVersionName("com.ss.android.article.news");
> ```


### shell.getApkPkgName(String filePath)
* @description 取得App文件的包名
* @param filePath 文件路径
* @return 字符串

> ```java
> String pkgName = shell.getApkPkgName("/sdcard/app.apk");
> ```


### shell.insertImageToAlbum(String path)
* @description 将图片插入到相册中，此方法会立刻更新相册数据
* @param path 图片路径

> ```java
> shell.insertImageToAlbum("/sdcard/a.png");
> ```


### shell.insertVideoToAlbum(String path)
* @description 将视频插入到相册中，此方法会立刻更新相册数据
* @param path 视频路径

> ```java
> shell.insertVideoToAlbum("/sdcard/a.mp4");
> ```



### shell.execCommand(String command)
* @description 执行Shell命令
* @param command 命令，例如安装App ： pm install /sdcard/app.apk
* @return 命令执行后返回的字符串结果

> ```java
> String result = shell.execCommand("pm install /sdcard/app.apk");
> ```



## 设备事件函数

## 图像识别函数


## TestCaseStarter说明
TestCaseStarter类是启动、停止脚本，云控截屏功能的集合,
TestCaseStarter.getInstance(context)直接取得实例.
### generateUiView(final String assetsFile, boolean bindEvent)
* @description 生成UI视图
* @param assetsFile 字符串，assets文件夹中的ui文件名称
* @param bindEvent 布尔型，是否绑定点击事件，如果绑定，将会点击启动按钮时候,自动启动脚本
* @return View 视图对象

        View view = TestCaseStarter.getInstance(context).generateUiView("ui.json",true);


### getUIParamJson(String assetsFile) 
* @description 取得UI界面的参数
* @param assetsFile 字符串，生成界面参数的配置文件名称
* @return JSONObject JSON数据结构的对象

        JSONObject json = TestCaseStarter.getInstance(context).getUIParamJson("ui.json");

## UI 定制说明

