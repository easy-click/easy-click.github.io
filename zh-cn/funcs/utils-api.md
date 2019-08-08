## utils.readConfigInt(JSONObject jsonObject,String key)
* @description 读取JSON中的整型数据
* @param jsonObject JSON对象
* @param key  配置项目
* @return 整型，找不到就返回0

> ```java
> int testData = utils.readConfigInt(jsonObject,"test_key");
> ```

## utils.readJSONString(JSONObject jsonObject, String key)
* @description 读取JSON中的字符串数据
* @param jsonObject JSON对象
* @param key        配置项目
* @return 字符串 找不到就返回空字符串

> ```java
> String testData = utils.readConfigString(jsonObject,"test_key");
> ```



## utils.isObjectNull(Object o)
* @description 判断一个对象为空
* @param o 对象
* @return true或者false

> ```java
> boolean isNull = utils.isObjectNull("test_key");
> ```




## utils.isObjectNotNull(Object o)
* @description 判断一个对象不为空
* @param o 对象
* @return true或者false

> ```java
> boolean isNull = utils.isObjectNotNull("test_key");
> ```




## utils.getRatio(float ratio)
* @description 取得比例，例如10参数，就是返回10%的比例，如果是true，说明随机比例正确，否则不正确
* @param ratio 浮点型 1-100
* @return true或者false

> ```java
> boolean ratio = utils.getRatio(20f);
> ```



## utils.getRangeInt(int min, int max)
* @description 取得某个范围的随机值
* @param min 最小值
* @param max 最大值
* @return 在min和max中间的值,包含最大和最小值

> ```java
> int value = utils.getRangeInt(1,100);
> ```


## utils.isTrue(Boolean r)
* @description 判断布尔型对象是否为真
* @param r 布尔型对象
* @return true 或者 false

> ```java
> boolean value = utils.isTrue(Boolean.valueOf("true"));
> ```


## utils.fileMd5(String file)
* @description 文件的MD5
* @param file 文件路径
* @return 文件MD5字符串或者null

> ```java
> String md5 = utils.fileMd5("/sdcard/a.txt");
> ```


## utils.dataMd5(String file)
* @description 数据计算出来的MD5
* @param data 数据
* @return 数据MD5字符串或者null

> ```java
> String md5 = utils.dataMd5("data");
> ```