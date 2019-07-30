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

        String imei = device.getImei();


## 文件操作函数
### file.readFile(String path)
* @description 将文件读取为字符串
* @param path 文件路径
* @return 字符串

        String data = file.readFile("/sdcard/test.txt");

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

