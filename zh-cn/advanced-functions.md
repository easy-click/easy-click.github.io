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

## Shell命令函数

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

