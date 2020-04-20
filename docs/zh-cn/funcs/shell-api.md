
# 说明
- 代理模式下才能使用该函数，用户执行shell命令
- shell模块的对象前缀是shell，例如 shell.installApp()这样调用


# 载入模块


> ```javascript
> loadECModule("shell");
> ```


## shell.installApp
* 安装 apk
* @param path 文件路径
* @return true 代表安装成功，false 代表安装失败

> ```javascript
> loadECModule("global");
> loadECModule("shell");
>     
> function main(){
>     var result = shell.installApp("/sdcard/app.apk");
> }
> main();
> ```


## shell.uninstallApp
* 卸载应用程序
* @param packageName 应用程序的包名
* @return true 代表卸载成功，false 代表卸载失败


> ```javascript
> loadECModule("global");
> loadECModule("shell");
>     
> function main(){
>     var result = shell.uninstallApp("com.ss.android.article.news");
> }
> main();
> ```



## shell.stopApp
* 停止正在执行的应用
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败


> ```javascript
> loadECModule("global");
> loadECModule("shell");
>     
> function main(){
>     var result = shell.stopApp("com.ss.android.article.news");
> }
> main();
> ```





## shell.execCommand
* 执行Shell命令
* @param command 命令，例如安装App ： pm install /sdcard/app.apk
* @return 命令执行后返回的字符串结果


> ```javascript
> loadECModule("global");
> loadECModule("shell");
>     
> function main(){
>     var result = shell.execCommand("pm install /sdcard/app.apk");
> }
> main();
> ```



