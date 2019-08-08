## event.toast(String msg)
* @description 显示消息
* @param msg 消息内容

> ```java
> event.toast("我是Toast消息");
> ```




## event.sleep(long miSecond)
* @description 线程休眠 单位是毫秒
* @param miSecond 毫秒

> ```java
> event.sleep(10*1000);
> ```




## event.click(int x, int y)
* @description 点击坐标点
* @param x X坐标
* @param y Y坐标
* @return true 点击成功，false点击失败

> ```java
> boolean r = event.click(100,100);
> ```

## event.drag(int startX, int startY, int endX, int endY, int steps)
* @description 执行从一个坐标到另一个坐标的拖动。您可以通过指定步骤的数目来控制平滑和刷新速度。每个步骤的执行被限制为每步5毫秒，所以对于100个步骤，刷新大约需要0.5秒完成
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
* @param keyCode 键盘的key，参见KeyEvent.KEYCODE_*
* @return true 代表成功 false代表失败

> ```java
> boolean r = event.pressKeyCode(KeyEvent.KEYCODE_A);
> ```

## event.pressKeyCode(int keyCode, int metaState)
* @description 模拟键盘输入
* @param keyCode 键盘的key，参见KeyEvent.KEYCODE_*
* @param metaState  控制按键，比如说shift键，alt键，ctrl键等控制键, 0或者 1
* @return true 代表成功 false代表失败

> ```java
> boolean r = event.pressKeyCode(KeyEvent.KEYCODE_A,1);
> ```

## event.inputText(Selector selector, String content)
* @description 输入内容
* @param selector 选择器
* @param content  内容字符串

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> event.inputText(selector, "我是文字");
> ```

## event.inputTextElement(String content, Selector... args)
* @description 通过Selector输入数据
* @param content  数据字符串
* @param args 选择器数组
* @return true 代表成功 false代表失

> ```java
> //第一种用法
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> boolean r = event.inputTextElement("我是文字", selector);
> //第二种用法，不能直接找到输入框，使用多个Selector组合选择器
> Selector selectorParent = Selector.builder().className("android.widget.LinearLayout").build();
> Selector selectorChild = Selector.builder().className("android.widget.EditText").build();
> boolean r1 = event.inputTextElement("我是文字", selectorParent, selectorChild);
> ```

## event.click(Selector obj)
* @description 点击选择器选中的元素
* @param obj 选择器
* @return true 成功 false 失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> event.click(selector);
> ```


## event.longClick(Selector obj)
* @description 长点击选择器选中的元素
* @param obj 选择器
* @return true 成功 false 失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> event.longClick(selector);
> ```


## event.exist(Selector obj)
* @description 判断某个元素是否存在
* @param obj 选择器
* @return true 成功 false 失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> event.exist(selector);
> ```


## event.elementInfo(Selector obj)
* @description 获取元素信息
* @param obj 元素选择器
* @return 元素信息对象或者null

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> ElementInfo el = event.elementInfo(selector);
> ```

## event.clickElement(ElementInfo elementInfo)
* @description 点击元素
* @param elementInfo 元素信息
* @return true 代表点击成功 false代表点击失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> ElementInfo el = event.elementInfo(selector);
> event.clickElement(el);
> ```

## event.clickElement(Selector... args)
* @description 通过Selector点击元素
* @param args Selector 数组
* @return true 代表点击成功 false代表点击失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> event.clickElement(selector);
> ```



## event.clickRandomElement(Selector... args)
* @description 通过Selector 随机点击元素，有可能Selector选中的是多个元素节点
* @param args Selector 数组
* @return true 代表点击成功 false代表点击失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> event.clickRandomElement(selector);
> ```



## event.getElementInfo(Selector... args)
* @description 通过Selector获取元素信息
* @param args Selector 数组
* @return ElementInfo 数组

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
>  ElementInfo[] els=event.getElementInfo(selector);
> ```


## event.getFirstElementInfo(Selector... args)
* @description 通过Selector获取元素信息，并返回第一个元素
* @param args Selector 数组
* @return ElementInfo 对象或者null

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
>  ElementInfo el=event.getFirstElementInfo(selector);
> ```



## event.takeElementScreenshot(String filePath, Selector... selector)
* @description 通过Selector 截取选中的元素截图,(底层命令截图 速度大概1-2秒)
* @param filePath 最终文件路径
* @param args Selector 数组
* @return true 代表成功 false代表失败

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> boolean r =event.takeElementScreenshot("/sdcard/a.png",selector);
> ```




## event.takeScreenshotBitmap()
* @description 截图 ,(底层命令截图 速度大概1-2秒)
* @return AutoImage 对象或者null

> ```java
> AutoImage r =event.takeScreenshotBitmap();
> ```


## event.dumpWindowHierarchy(boolean compressed)
* @description 获取当前的视图为XML格式，并保存到文件中
* @param compressed 是否压缩
* @return 文件路径

> ```java
> String r =event.dumpWindowHierarchy(false);
> ```

## event.getText(Selector obj)
* @description 获取文本
* @param obj 元素选择器
* @return 文本字符串

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> String r =event.getText(selector);
> ```



## event.getTextBySelector(Selector... args)
* @description 获取文本
* @param args 选择器数组
* @return 文本字符串

> ```java
> Selector selector = Selector.builder().className("android.widget.EditText").build();
> String r =event.getTextBySelector(selector);
> ```


## event.execShellCommand(String command)
* @description 执行shell命令
* @param command 命令字符串
* @return shell结果

> ```java
> String r =event.execShellCommand("pm install -r /sdcard/a.apk");
> ```

## event.getRunningActivity()
* @description 取得当前运行的Activity类名
* @return 类名字符串

> ```java
> String r =event.getRunningActivity();
> ```


## event.getRunningActivity()
* @description 取得当前运行的App包名
* @return 包名字符串

> ```java
> String r =event.getRunningPkg();
> ```



## event.getLastToast()
* @description 取得最近的Toast消息
* @return null代表无消息

> ```java
> ToastInfo r =event.getLastToast();
> ```


## event.getLastNotification()
* @description 取得最近的通知栏消息
* @return null代表无消息

> ```java
> NotificationInfo r =event.getLastNotification();
> ```



## event.getLastNotification()
* @description 将通知发射处理，相当于点击了通知栏
* @param seqId 通知信息的序列号
* @return true 代表发射通知成功

> ```java
> NotificationInfo r =event.getLastNotification();
> event.shotNotification(r.seqId);
> ```



- 更多函数请查看javadoc