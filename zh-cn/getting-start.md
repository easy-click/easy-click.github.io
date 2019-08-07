### 加入类库
- 在Android Studio 项目中 build.gradle 文件中加入私服仓库
> ```gradle
maven {
    url "https://raw.githubusercontent.com/easy-click/sdk-repo/master/"
}
> ```

- 加入类库引用
> ```gradle
implementation 'com.android.support:appcompat-v7:26.0.0'
implementation 'com.android.support:design:26.0.0'
implementation group: 'com.android.support', name: 'support-v4', version: '26.0.0'
implementation group: 'com.gibb', name: 'easyclick', version: '1.0.9-no-image', ext: 'aar'
> ```


 
### 配置UI界面

- 新建Activity类并配置为启动类
- 在Android工程res/layout/文件夹新建一个main.xml文件,内容为

> ```xml
> <?xml version="1.0" encoding="utf-8"?>
> <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
>     android:layout_width="match_parent"
>     android:layout_height="match_parent"
>     android:orientation="vertical">
> 
>     <TextView
>         android:layout_width="match_parent"
>         android:layout_height="wrap_content"
>         android:text="第一个DEMO" />
> </LinearLayout>
> ```

- 设置界面UI

> ```java
>     protected void onCreate(Bundle savedInstanceState) {
>         super.onCreate(savedInstanceState);
>         View view = ApiStarter.getInstance(getApplicationContext())
>                 .generateUiView("main.xml", true);
>         setContentView(view);
>     }
> 
> ```



### 编写主任务

- 新建 com.run.Main 类 并继承 com.gibb.auto.open.BaseCaseMain

> ```java
> package com.run;
> import com.gibb.auto.open.BaseCaseMain;
> public class Main extends BaseCaseMain {
>     @Override
>     public void exec() {
>         event.toast("我是DEMO");
>     }
> }
> ```


### 运行与调试

- 如果机器已经root过，请在运行的时候对APP进行授权
- 如果非Root机器，请查看请查看[环境构建工具](zh-cn/dev-tools)

?> 运行和调试都按照Android的标准步骤即可，注意需要关闭 Instant Run 功能。[如何关闭 Instant Run](https://blog.csdn.net/yu544324974/article/details/52472641)



### 混淆配置
- 根据实际情况，可以不开启



> ```proguard
> -keep class android.support.**{*;}
> -keep public class * extends android.support.v4.app.Fragment
> -keep public class * extends android.support.**
> -keep public class * extends android.test.**
> -keep class org.opencv.**{*;}
> -keep class com.gibb.auto.model.**{*;}
> -keep class **.Main{*;}
> -keep class **.R {*;}
> -keep class **.R$* {*;}
> -keep class **.R$*
> -keep class **.R
> ```













