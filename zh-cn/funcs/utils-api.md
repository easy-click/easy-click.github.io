## utils.readConfigInt(JSONObject jsonObject,String key)
* @description 读取JSON中的整型数据
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param jsonObject JSON对象
* @param key  配置项目
* @return 整型，找不到就返回0

> ```java
> int testData = utils.readConfigInt(jsonObject,"test_key");
> ```

## utils.readJSONString(JSONObject jsonObject, String key)
* @description 读取JSON中的字符串数据
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param jsonObject JSON对象
* @param key        配置项目
* @return 字符串 找不到就返回空字符串

> ```java
> String testData = utils.readConfigString(jsonObject,"test_key");
> ```



## utils.isObjectNull(Object o)
* @description 判断一个对象为空
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param o 对象
* @return true或者false

> ```java
> boolean isNull = utils.isObjectNull("test_key");
> ```




## utils.isObjectNotNull(Object o)
* @description 判断一个对象不为空
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param o 对象
* @return true或者false

> ```java
> boolean isNull = utils.isObjectNotNull("test_key");
> ```




## utils.getRatio(float ratio)
* @description 取得比例，例如10参数，就是返回10%的比例，如果是true，说明随机比例正确，否则不正确
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param ratio 浮点型 1-100
* @return true或者false

> ```java
> boolean ratio = utils.getRatio(20f);
> ```



## utils.getRangeInt(int min, int max)
* @description 取得某个范围的随机值
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param min 最小值
* @param max 最大值
* @return 在min和max中间的值,包含最大和最小值

> ```java
> int value = utils.getRangeInt(1,100);
> ```


## utils.isTrue(Boolean r)
* @description 判断布尔型对象是否为真
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param r 布尔型对象
* @return true 或者 false

> ```java
> boolean value = utils.isTrue(Boolean.valueOf("true"));
> ```


## utils.fileMd5(String file)
* @description 文件的MD5
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param file 文件路径
* @return 文件MD5字符串或者null

> ```java
> String md5 = utils.fileMd5("/sdcard/a.txt");
> ```


## utils.dataMd5(String file)
* @description 数据计算出来的MD5
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param data 数据
* @return 数据MD5字符串或者null

> ```java
> String md5 = utils.dataMd5("data");
> ```



## utils.randomInt(int length)
* @description 随机整型数据
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param length 位数，要随机产生多少位的整型数据
* @return 整型

> ```java
> int r = utils.randomInt(2);
> ```

## utils.randomCharNumber(int length)
* @description 取得随机的数字和字母
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param length 长度
* @return 字符串数字混合

> ```java
> String r = utils.randomCharNumber(2);
> ```




## utils.getApkPkgName(String filePath)
* @description 取得App文件的包名
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param filePath 文件路径
* @return 字符串

> ```java
> String pkgName = utils.getApkPkgName("/sdcard/app.apk");
> ```


## utils.insertImageToAlbum(String path)
* @description 将图片插入到相册中，此方法会立刻更新相册数据
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param path 图片路径

> ```java
> utils.insertImageToAlbum("/sdcard/a.png");
> ```


## utils.insertVideoToAlbum(String path)
* @description 将视频插入到相册中，此方法会立刻更新相册数据
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param path 视频路径

> ```java
> utils.insertVideoToAlbum("/sdcard/a.mp4");
> ```


## utils.openApp(String packageName)
* @description 打开APP
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param packageName 应用程序的包名
* @return true 代表成功，false 代表失败

> ```java
> boolean result = utils.openApp("com.ss.android.article.news");
> ```


## utils.isAppExist(String packageName)
* @description App是否已经安装
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param packageName 应用程序的包名
* @return true 代表已经安装，false代表未安装

> ```java
> boolean result = utils.isAppExist("com.ss.android.article.news");
> ```

## utils.getAppVersionCode(String packageName)
* @description 取得已安装的程序的版本整型标示
* 运行环境: 无限制
* 兼容版本: Android 4.4 以上
* @param packageName 应用程序的包名
* @return 整型

> ```java
> int versionCode = shell.getAppVersionCode("com.ss.android.article.news");
> ```

