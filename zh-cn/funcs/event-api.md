## NodeSelectors 元素选择器说明
 - NodeSelectors 是元素选择器，使用链式函数构建，例如NodeSelectors.get().className("android.widget.EditText");
 - NodeSelectors 中的字段方法和元素属性一一对应，具体可以查看 [EasyClick环境构建软件](zh-cn/dev-tools?id=easyclick-环境构建软件)
 - 事件函数中，使用 NodeSelectors 作为参数的，可以使用递进式选择元素，用于应对一次性无法选中元素的情况




## event.toast(String msg)
* @description 显示消息
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param msg 消息内容

> ```java
> event.toast("我是Toast消息");
> ```




## event.sleep(long miSecond)
* @description 线程休眠 单位是毫秒
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param miSecond 毫秒

> ```java
> event.sleep(10*1000);
> ```




## event.click(int x, int y)
* @description 点击坐标点
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param x X坐标
* @param y Y坐标
* @return true 点击成功，false点击失败

> ```java
> boolean r = event.click(100,100);
> ```

## event.drag(int startX, int startY, int endX, int endY, int steps)
* @description 执行从一个坐标到另一个坐标的拖动。您可以通过指定步骤的数目来控制平滑和刷新速度。每个步骤的执行被限制为每步5毫秒，所以对于100个步骤，刷新大约需要0.5秒完成
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param startX 起始坐标的X轴值
* @param startY 起始坐标的Y轴值 
* @param endX   结束坐标的X轴值
* @param endY   结束坐标的Y轴值
* @param steps  拖动操作的步骤数 
* @return true true 拖动成功, false 拖动失败

> ```java
> boolean r = event.drag(100,100,300,300,100);
> ```



## event.swipe(int startX, int startY, int endX, int endY, int steps)
* @description 执行从一个坐标到另一个坐标的滑动。您可以通过指定步骤的数目来控制平滑和刷新速度。每个步骤的执行被限制为每步5毫秒，所以对于100个步骤，刷新大约需要0.5秒完成
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param startX 起始坐标的X轴值
* @param startY 起始坐标的Y轴值 
* @param endX   结束坐标的X轴值
* @param endY   结束坐标的Y轴值
* @param steps  滑动操作的步骤数 
* @return true  滑动成功, false 滑动失败

> ```java
> boolean r = event.swipe(100,100,300,300,100);
> ```

## event.injectInputEvent(int action, float x, float y, int metaState)
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @description 执行输入事件
* @param action 动作，请看类:  MotionEvent.ACTION_*
* @param x         x坐标 
* @param y         y坐标
* @param metaState  控制按键，比如说shift键，alt键，ctrl键等控制键, 0或者 1
* @return true 代表成功 false代表失败

> ```java
> boolean r =event.injectInputEvent(MotionEvent.ACTION_DOWN, 100, 100, 0);
> ```


## event.pressKeyCode(int keyCode)
* @description 模拟键盘输入
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param keyCode 键盘的key，参见KeyEvent.KEYCODE_*
* @return true 代表成功 false代表失败

> ```java
> boolean r = event.pressKeyCode(KeyEvent.KEYCODE_A);
> ```

## event.pressKeyCode(int keyCode, int metaState)
* @description 模拟键盘输入
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param keyCode 键盘的key，参见KeyEvent.KEYCODE_*
* @param metaState  控制按键，比如说shift键，alt键，ctrl键等控制键, 0或者 1
* @return true 代表成功 false代表失败

> ```java
> boolean r = event.pressKeyCode(KeyEvent.KEYCODE_A,1);
> ```

## event.inputText(NodeSelectors selectors, String content)
* @description 输入内容
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param selector 选择器
* @param content  内容字符串

> ```java
> NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> event.inputText(selector, "我是文字");
> ```

## event.setCurrentIme()
* @description 设置当前的输入法，用于输入数据
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @return true 代表成功 false代表失

> ```java
> boolean r = event.setCurrentIme();
> ```


## event.imeInputText(NodeSelectors selectors, String content)
* @description 使用输入法输入内容
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param content  数据字符串
* @param args 选择器数组
* @return true 代表成功 false代表失

> ```java
> NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> boolean r = event.imeInputText("我是文字", selector);
> ```

## event.click(NodeSelectors selectors)
* @description 点击选择器选中的元素
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param obj 选择器
* @return true 成功 false 失败

> ```java
> NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> event.click(selector);
> ```


## event.longClick(NodeSelectors selectors)
* @description 长点击选择器选中的元素
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param obj 选择器
* @return true 成功 false 失败

> ```java
> NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> event.longClick(selector);
> ```


## event.has(NodeSelectors selectors)
* @description 判断某个元素是否存在
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param obj 选择器
* @return true 成功 false 失败

> ```java
>NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> event.has(selector);
> ```






## event.takeNodeScreenshot(NodeSelectors selectors,String filePath)
* @description 通过 NodeSelectors 截取选中的元素截图,(底层命令截图 速度大概1-2秒)
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param filePath 最终文件路径
* @param args Selector 数组
* @return true 代表成功 false代表失败

> ```java
> NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> boolean r =event.takeNodeScreenshot("/sdcard/a.png",selector);
> ```




## event.takeScreenshotImage()
* @description 截图 ,(底层命令截图 速度大概1-2秒)
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @return AutoImage 对象或者null

> ```java
> AutoImage r =event.takeScreenshotImage();
> ```


## event.dumpWindowHierarchy(boolean compressed)
* @description 获取当前的视图为XML格式，并保存到文件中
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param compressed 是否压缩
* @return 文件路径

> ```java
> String r =event.dumpWindowHierarchy(false);
> ```

## event.getText(NodeSelectors selectors)
* @description 获取文本
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param selectors 元素选择器
* @return 文本字符串集合

> ```java
> NodeSelectors selector = NodeSelectors.get().className("android.widget.EditText");
> List<String> r =event.getText(selector);
> ```



## event.execShellCommand(String command)
* @description 执行shell命令
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param command 命令字符串
* @return shell结果

> ```java
> String r =event.execShellCommand("pm install -r /sdcard/a.apk");
> ```

## event.getRunningActivity()
* @description 取得当前运行的Activity类名
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @return 类名字符串

> ```java
> String r =event.getRunningActivity();
> ```


## event.getRunningActivity()
* @description 取得当前运行的App包名
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @return 包名字符串

> ```java
> String r =event.getRunningPkg();
> ```



## event.getLastToast()
* @description 取得最近的Toast消息
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @return null代表无消息

> ```java
> ToastInfo r =event.getLastToast();
> ```


## event.getLastNotification()
* @description 取得最近的通知栏消息
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @return null代表无消息

> ```java
> NotificationInfo r =event.getLastNotification();
> ```



## event.getLastNotification()
* @description 将通知发射处理，相当于点击了通知栏
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param seqId 通知信息的序列号
* @return true 代表发射通知成功

> ```java
> NotificationInfo r =event.getLastNotification();
> event.shotNotification(r.seqId);
> ```

## event.swipe(NodeSelectors selectors, int endX, int endY, int steps)
* @description 滑动元素到某个坐标点
* 运行环境: 代理模式
* 兼容版本: Android 4.4 以上
* @param selectors 节点选择器
* @param endX      结束的X坐标
* @param endY      结束的Y坐标
* @param steps     滑动步数，越大，滑动时间越长
* @return true 滑动成功，false 滑动失败



- 更多函数请查看javadoc