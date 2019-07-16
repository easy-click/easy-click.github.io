### 加入类库
    在Android Studio中加入私服仓库
### 定义入口类

### 编写主任务

### 编写子任务

### 运行与调试

### 打包发布

### 混淆配置

> ```java
> String x = "string";
> String y = "string";
> String z = new String("string");
> 
> System.out.println("x == y:"+(x == y)); //true
> System.out.println("x == y:"+(x == z)); //false
> 
> System.out.println("x.equals(y):"+x.equals(y)); // true
> System.out.println("x.equals(z):"+x.equals(z)); // true
> ```