
-- 注意: 这里的截图函数需要Andrioid 5.0 以上版本才能使用, 5.0 以下请使用event函数的截图方法

## image.requestScreenCapture()
* @description 向系统申请屏幕截图权限，返回是否请求成功。
    * 第一次使用该函数会弹出截图权限请求，建议选择“总是允许”。
    * 这个函数只是申请截图权限，并不会真正执行截图，真正的截图函数是captureScreen()。
    * 该函数在截图脚本中只需执行一次，而无需每次调用captureScreen()都调用一次。
    * 建议在本软件界面运行该函数，在其他软件界面运行时容易出现一闪而过的黑屏现象。


* 运行环境: 无限制
* 兼容版本: Android 5.0 以上 
* @return true 代表成功 false代表失败

> ```java
> boolean request = image.requestScreenCapture();
> ```


## image.requestScreenCapture(int orientation)
* @description 向系统申请屏幕截图权限，返回是否请求成功。
    * 第一次使用该函数会弹出截图权限请求，建议选择“总是允许”。
    * 这个函数只是申请截图权限，并不会真正执行截图，真正的截图函数是captureScreen()。
    * 该函数在截图脚本中只需执行一次，而无需每次调用captureScreen()都调用一次。
    * 建议在本软件界面运行该函数，在其他软件界面运行时容易出现一闪而过的黑屏现象。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param orientation 屏幕方向，1 代表竖屏  2 代表横屏
* @return true 代表成功 false代表失败

> ```java
> boolean request = image.requestScreenCapture(1);
> ```


## image.releaseScreenCapture()
* @description 释放截屏请求

> ```java
> image.releaseScreenCapture();
> ```



## image.captureScreen()
* @description 截取当前屏幕并返回一个Image对象。
    * 没有截图权限时执行该函数会返回null
    * 两次调用可能返回相同的Image对象。这是因为设备截图的更新需要一定的时间，短时间内（一般来说是16ms）连续调用则会返回同一张截图。
    * 截图需要转换为Bitmap格式，从而该函数执行需要一定的时间(0~20ms)。
    * 另外在requestScreenCapture()执行成功后需要一定时间后才有截图可用，因此如果立即调用captureScreen()，会等待一定时间后(一般为几百ms)才返回截图。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @return AutoImage对象或者null

> ```java
> AutoImage image = image.captureScreen();
> ```


## image.captureScreen(String path)
* @description 截取当前屏幕并以PNG格式保存到path中。如果文件不存在会被创建；文件存在会被覆盖。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param path 截图保存路径
* @return true 截图成功 false 代表不成功

> ```java
> boolean cap = image.captureScreen("/sdcard/a.png");
> ```

## image.readImage(String path)
* @description 读取在路径path的图片文件并返回一个{@link AutoImage}对象。如果文件不存在或者文件无法解码则返回null。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param path 图片路径
* @return AutoImage 对象或者null

> ```java
> AutoImage autoimg = image.readImage("/sdcard/a.png");
> ```

## image.readBitmap(String path)
* @description 读取在路径path的图片文件并返回一个{@link AutoImage}对象。如果文件不存在或者文件无法解码则返回null。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param path 图片路径
* @return android的bitmap对象或者null

> ```java
> Bitmap autoimg = image.readBitmap("/sdcard/a.png");
> ```


## image.pixelInImage(AutoImage image, int x, int y)
* @description 返回图片image在点(x, y)处的像素的ARGB值。该值的格式为0xAARRGGBB，是一个"32位整数",坐标系以图片左上角为原点。以图片左侧边为y轴，上侧边为x轴。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param image 图片
* @param x     要获取的像素的横坐标。
* @param y     要获取的像素的纵坐标。
* @return 整型

> ```java
> AutoImage image = image.captureScreen()
> int color = image.pixelInImage(image,100,100);
> ```




## image.findImage(AutoImage image, AutoImage template)
* @description 找图。在大图片image中查找小图片template的位置（模块匹配），找到时返回位置坐标区域(Rect)，找不到时返回null。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param image 大图片
* @param template 小图片（模板）
* @return com.gibb.auto.model.Rect 区域坐标对象或者null

> ```java
> AutoImage image = image.captureScreen()
> AutoImage template = image.readImage("/sdcard/a.png")
> Rect rect = image.findImage(image,template);
> ```


## image.findColorEquals(AutoImage autoImage, int color)
* @description 在图片img指定区域中找到颜色和color完全相等的某个点，并返回该点的左边；如果没有找到，则返回null。
* 运行环境: 无限制
* 兼容版本: Android 5.0 以上
* @param image 大图片
* @param color     要寻找的颜色 
* @return com.gibb.auto.model.Point 坐标点或者null

> ```java
> AutoImage image = image.captureScreen()
> Point rect = image.findColorEquals(image,0x982844);
> ```


- 更多函数请查看javadoc