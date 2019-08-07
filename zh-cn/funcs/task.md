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
    - utils 变量: 常用工具类操作相关的Api封装
    - thread 变量: 多线程相关的Api封装


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



## isStop()

* @description 任务是否结束
* @return true 结束， false 未结束

> ```java
> boolean value = isStop();
> ```