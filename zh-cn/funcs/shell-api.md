

## shell.installApp(String path)
* @description 安装 apk
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param path 文件路径
* @return true 代表安装成功，false 代表安装失败

> ```java
> boolean result = shell.installApp("/sdcard/app.apk");
> ```


## shell.uninstallApp(String packageName)
* @description 卸载应用程序
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param packageName 应用程序的包名
* @return true 代表卸载成功，false 代表卸载失败

> ```java
> boolean result = shell.uninstallApp("com.ss.android.article.news");
> ```



## shell.stopApp(String packageName)
* @description 停止正在执行的应用
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败

> ```java
> boolean result = shell.stopApp("com.ss.android.article.news");
> ```





## shell.execCommand(String command)
* @description 执行Shell命令
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param command 命令，例如安装App ： pm install /sdcard/app.apk
* @return 命令执行后返回的字符串结果

> ```java
> String result = shell.execCommand("pm install /sdcard/app.apk");
> ```
