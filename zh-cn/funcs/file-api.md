
## file.readFile(String path)
* @description 将文件读取为字符串
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param path 文件路径
* @return 字符串

> ```java
> String data = file.readFile("/sdcard/test.txt");
> ```


## file.writeFile(String data, String path)
* @description 将字符串存储到文件中
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param data 字符串 数据
* @param path 文件路径

> ```java
> String data="Test";
> file.writeFile(data,"/sdcard/test.txt");
> ```


## file.create(String path)
* @description 创建一个文件或者文件夹
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param path 文件或者文件夹路径
* @return 布尔型 true 代表创建成功

> ```java
> boolean create=file.create("/sdcard/test.txt");
> ```        

## file.readAssets(String path)
* @description 从APK的assets文件夹中读取数据为字符串
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param path assets文件夹中的文件路径，例如 data/a.txt
* @return 字符串

> ```java
> String data=file.readAssets("data/test.txt");
> ```


## file.deleteAllFile(String path)
* @description 删除所有文件或者文件夹
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param path 文件或者文件路径

> ```java
> file.deleteAllFile("data/test.txt");
> ```
