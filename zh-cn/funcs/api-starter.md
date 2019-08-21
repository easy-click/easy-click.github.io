## 类说明
- ApiStarter类是启动、停止脚本，云控截屏功能的集合
- ApiStarter.getInstance(context)直接取得实例


## setRunningMode(int mode)) 
* @description 设置运行模式
*  @param mode 1 代理模式，2 代表无障碍模式


## version() 
* @description SDK版本
* @return 字符串

> ```java
> String version = ApiStarter.getInstance(context).version();
> ```


## updateApp(Activity activity, String url) 
* @description 更新App,如果有更新，将会根据配置进行静默安装或者弹窗之类的
* @param activity Activity对象，用来展示升级对话框
* @param url 更新的地址URL


> ```java
> ApiStarter.getInstance(context).updateApp(this,"http://192.168.1.131/update.json");
> ```

## generateUiView(final String layoutFileName, boolean bindEvent)
* @description 生成UI视图
* @param layoutFileName 字符串，layout文件夹中的UI名称
* @param bindEvent 布尔型，是否绑定点击事件，如果绑定，将会点击启动按钮时候,自动启动脚本
* @return View 视图对象

> ```java
> View view = ApiStarter.getInstance(context).generateUiView("main.xml",true);
> ```
        


## getUIParamJson(String assetsFile) 
* @description 取得UI界面的参数
* @param layoutFileName 生成界面参数的配置文件名称
* @return JSONObject JSON数据结构的对象

> ```java
> JSONObject json = ApiStarter.getInstance(context).getUIParamJson("ui.json");
> ```
        

## showFloatControlForUi(final String uiFile)
* @description 显示浮窗控制按钮，浮窗控制包含了开始 、停止 、打开主界面三个功能，如果有多个UI界面，需要再这个参数中进行配置
* @param uiFile layout文件夹中的 UI界面配置的文件名称，例如 main.xml

> ```java
> ApiStarter.getInstance(context).showFloatControlForUi("main.xml");
> ```

## setDefaultClass(String defaultClass) 
* @description 设置默认启动任务类名
* @param defaultClass 类名称


> ```java
> ApiStarter.getInstance(context).setDefaultClass(Main.class.getName());
> ```
        

## start(JSONObject paramJson) 
* @description 启动脚本, 使用默认类名
* @param paramJson 参数JSON对象，会传递给实际的任务类


> ```java
> JSONObject paramJson =new JSONObject();
> ApiStarter.getInstance(context).start(paramJson);
> ```
        



## start(JSONObject paramJson,, String className) 
* @description 启动脚本, 使用默认类名
* @param paramJson 参数JSON对象，会传递给实际的任务类
* @param className 任务入口类名，例如 com.run.Main


> ```java
> JSONObject paramJson =new JSONObject();
> TestCaseStarter.getInstance(context).start(paramJson,Main.class.getName());
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
> boolean screenCapture=ApiStarter.getInstance(context).requestScreenCapture();
> ```

## requestScreenCapture(boolean landscape) 
* @description 请求截屏 5.0 以上版本才能使用，这里如果弹出授权框，请进行运行
* @param landscape 1 竖屏  2 横屏
* @return true 代表成功 false 代表失败

> ```java
> boolean screenCapture=ApiStarter.getInstance(context).requestScreenCapture(1);
> ```




## captureScreen() 
* @description 截屏函数，5.0以上版本才能使用
* @return AutoImage 对象

> ```java
> AutoImage screen=ApiStarter.getInstance(context).captureScreen();
> ```




## releaseScreenCapture() 
* @description 释放截屏

> ```java
> ApiStarter.getInstance(context).releaseScreenCapture();
> ```


