

## shell.installApp(String path)
* @description 安装 apk
* @param path 文件路径
* @return true 代表安装成功，false 代表安装失败

> ```java
> boolean result = shell.installApp("/sdcard/app.apk");
> ```


## shell.uninstallApp(String packageName)
* @description 卸载应用程序
* @param packageName 应用程序的包名
* @return true 代表卸载成功，false 代表卸载失败

> ```java
> boolean result = shell.uninstallApp("com.ss.android.article.news");
> ```


## shell.openApp(String packageName)
* @description 打开APP
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败

> ```java
> boolean result = shell.openApp("com.ss.android.article.news");
> ```

## shell.stopApp(String packageName)
* @description 停止正在执行的应用
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败

> ```java
> boolean result = shell.stopApp("com.ss.android.article.news");
> ```



## shell.isAppExist(String packageName)
* @description App是否已经安装
* @param packageName 应用程序的包名
* @return true 代表已经安装，false代表未安装

> ```java
> boolean result = shell.isAppExist("com.ss.android.article.news");
> ```

## shell.getAppVersionCode(String packageName)
* @description 取得已安装的程序的版本整型标示
* @param packageName 应用程序的包名
* @return 整型

> ```java
> int versionCode = shell.getAppVersionCode("com.ss.android.article.news");
> ```


## shell.getAppVersionCode(String packageName)
* @description 取得已安装的程序的版本字符串标示
* @param packageName 应用程序的包名
* @return 字符串，例如 1.0.0

> ```java
> String versionName = shell.getAppVersionName("com.ss.android.article.news");
> ```


## shell.getApkPkgName(String filePath)
* @description 取得App文件的包名
* @param filePath 文件路径
* @return 字符串

> ```java
> String pkgName = shell.getApkPkgName("/sdcard/app.apk");
> ```


## shell.insertImageToAlbum(String path)
* @description 将图片插入到相册中，此方法会立刻更新相册数据
* @param path 图片路径

> ```java
> shell.insertImageToAlbum("/sdcard/a.png");
> ```


## shell.insertVideoToAlbum(String path)
* @description 将视频插入到相册中，此方法会立刻更新相册数据
* @param path 视频路径

> ```java
> shell.insertVideoToAlbum("/sdcard/a.mp4");
> ```



## shell.execCommand(String command)
* @description 执行Shell命令
* @param command 命令，例如安装App ： pm install /sdcard/app.apk
* @return 命令执行后返回的字符串结果

> ```java
> String result = shell.execCommand("pm install /sdcard/app.apk");
> ```
