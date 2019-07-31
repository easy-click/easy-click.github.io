## 类说明
- TestCaseStarter类是启动、停止脚本，云控截屏功能的集合
- TestCaseStarter.getInstance(context)直接取得实例



## version() 
* @description SDK版本
* @return 字符串



> ```java
> String version = TestCaseStarter.getInstance(context).version();
> ```
        


## generateUiView(final String assetsFile, boolean bindEvent)
* @description 生成UI视图
* @param assetsFile 字符串，assets文件夹中的ui文件名称
* @param bindEvent 布尔型，是否绑定点击事件，如果绑定，将会点击启动按钮时候,自动启动脚本
* @return View 视图对象

> ```java
> View view = TestCaseStarter.getInstance(context).generateUiView("ui.json",true);
> ```
        


## getUIParamJson(String assetsFile) 
* @description 取得UI界面的参数
* @param assetsFile 字符串，生成界面参数的配置文件名称
* @return JSONObject JSON数据结构的对象

> ```java
> JSONObject json = TestCaseStarter.getInstance(context).getUIParamJson("ui.json");
> ```
        


## setDefaultClass(String defaultClass) 
* @description 设置默认启动任务类名
* @param defaultClass 类名称


> ```java
> TestCaseStarter.getInstance(context).setDefaultClass(Main.class.getName());
> ```
        

## startMin(JSONObject paramJson) 
* @description 启动脚本, 使用默认类名
* @param paramJson 参数JSON对象，会传递给实际的任务类


> ```java
> JSONObject paramJson =new JSONObject();
> TestCaseStarter.getInstance(context).startMin(paramJson);
> ```
        



## startMin(JSONObject paramJson,, String className) 
* @description 启动脚本, 使用默认类名
* @param paramJson 参数JSON对象，会传递给实际的任务类
* @param className 任务入口类名，例如 com.run.Main


> ```java
> JSONObject paramJson =new JSONObject();
> TestCaseStarter.getInstance(context).startMin(paramJson,Main.class.getName());
> ```



## stopCurrent(JSONObject paramJson,, String className) 
* @description 停止当前的脚本用例
* @return true 代表成功 false 代表失败

> ```java
> TestCaseStarter.getInstance(context).stopCurrent();
> ```

## requestScreenCapture() 
* @description 请求截屏 5.0 以上版本才能使用，这里如果弹出授权框，请进行运行
* @return true 代表成功 false 代表失败

> ```java
> boolean screenCapture=TestCaseStarter.getInstance(context).requestScreenCapture();
> ```

## requestScreenCapture(boolean landscape) 
* @description 请求截屏 5.0 以上版本才能使用，这里如果弹出授权框，请进行运行
* @param landscape 1 竖屏  2 横屏
* @return true 代表成功 false 代表失败

> ```java
> boolean screenCapture=TestCaseStarter.getInstance(context).requestScreenCapture(1);
> ```




## captureScreen() 
* @description 截屏函数，5.0以上版本才能使用
* @return AutoImage 对象

> ```java
> AutoImage screen=TestCaseStarter.getInstance(context).captureScreen();
> ```




## releaseScreenCapture() 
* @description 释放截屏

> ```java
> TestCaseStarter.getInstance(context).releaseScreenCapture();
> ```


