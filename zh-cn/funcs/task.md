## 任务划分说明
 - 主任务和子任务无本质区别，只是逻辑上区分而已
 - 主任务继承com.gibb.auto.open.BaseCaseMain
 - 子任务继承com.gibb.auto.open.testcase.SubTestCase
 - 子任务和主任务都包含了相同的功能函数，只要继承即可拥有以下能力:
    - device 变量: 设备相关的API封装
    - event 变量: Ui事件相关的API封装   
    - file 变量: 文件操作相关的API封装
    - http 变量: HTTP网络操作相关的封装
    - image 变量: 图像相关的API封装
    - shell 变量: Shell命令操作相关的Api封装


!> 任务类中函数解析

## readConfigInt(String key)
* @description 读取UI界面中的参数,返回是整型
* @param key 在UI界面中配置的key
* @return 整型，找不到就返回0

> ```java
> int testData = readConfigInt("test_key");
> ```

## readConfigString(String key)
* @description 读取UI界面中的参数,返回是整型
* @param key 在UI界面中配置的key
* @return 字符串 找不到就返回空字符串

> ```java
> String testData = readConfigString("test_key");
> ```



## isObjectNull(Object o)
* @description 判断一个对象为空
* @param o 对象
* @return true或者false

> ```java
> boolean isNull = isObjectNull("test_key");
> ```




## isObjectNotNull(Object o)
* @description 判断一个对象不为空
* @param o 对象
* @return true或者false

> ```java
> boolean isNull = isObjectNotNull("test_key");
> ```




## getRatio(float ratio)
* @description 取得比例，例如10参数，就是返回10%的比例，如果是true，说明随机比例正确，否则不正确
* @param ratio 浮点型 1-100
* @return true或者false

> ```java
> boolean ratio = getRatio(20f);
> ```



## getRangeInt(int min, int max)
* @description 取得某个范围的随机值
* @param min 最小值
* @param max 最大值
* @return 在min和max中间的值,包含最大和最小值

> ```java
> int value = getRangeInt(1,100);
> ```


## isTrue(Boolean r)
* @description 判断布尔型对象是否为真
* @param r 布尔型对象
* @return true 或者 false

> ```java
> boolean value = isTrue(Boolean.valueOf("true"));
> ```
 

## execFuncAndWait(ExecFunc condition, long timeout)
* @description 执行某个函数并且等待true返回，如果函数中返回的是true，该方法将立刻执行完毕
* @param condition 条件函数
* @param timeout   超时时间，单位是秒
* @return 返回一个布尔型对象
> ```java
>  //演示打开微信的监测，超时时间为10秒，如果10秒都为打开，说明打开微信失败了
>        Boolean openMM = execFuncAndWait(new ExecFunc() {
>            @Override
>            public Boolean execute() {
>
>                if (currentIsMM()) {
>                    return true;
>                }
>                return false;
>            }
>        }, 10);
>        if (isTrue(openMM)) {
>            event.toast("打开了微信");
>        } else {
>            event.toast("未打开微信");
>        }
> ```



## execFuncAndWaitNotNull(ExecFunc condition, long timeout) 
* @description 执行某个函数并且等待结果不为空时返回，如果函数中返回的不是空，该方法将立刻执行完毕
* @param condition 条件函数
* @param timeout   超时时间，单位是秒
* @return 返回一个泛型返回值
> ```java
> NotificationInfo notificationInfo = execFuncAndWaitNotNull(new ExecFunc<NotificationInfo>() {
>            @Override
>            public NotificationInfo execute() {
>                NotificationInfo notificationInfo = event.getLastNotification();
>                if (notificationInfo != null) {
>                    if (notificationInfo.text != null && notificationInfo.text.contains("红包")) {
>                        return notificationInfo;
>                    }
>                }
>                return notificationInfo;
>            }
>        }, 20);
>        if (isObjectNotNull(notificationInfo)) {
>            event.toast("找到了红包");
>        } else {
>            event.toast("未找到了红包");
>        }
> ```


## isStop()

* @description 任务是否结束
* @return true 结束， false 未结束

> ```java
> boolean value = isStop();
> ```