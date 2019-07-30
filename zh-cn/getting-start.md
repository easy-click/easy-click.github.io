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
implementation group: 'com.gibb', name: 'easyclick', version: '1.0.7', ext: 'aar'
> ```


 
### 配置UI界面

- 新建Activity类并配置为启动类
- 在Android工程assets文件夹新建一个demo.json文件,内容为

> ```json
> {
> 	"ui": [{
> 		"label": "测试文本",
> 		"line_type": "文本",
> 		"background_color": "#e67f7f"
> 	}]
> }
> ```

- EasyClick 自带 TestCaseStarter#generateUiView 方法，通过JSON配置，即可生成脚本参数UI界面



### 编写主任务

- 新建 com.run.Main 类 并继承 com.gibb.auto.open.BaseCaseMain

?> 主任务是指包含子任务的入口集合，为了更清晰，逻辑上划分的主、子任务

- 在com.run.Main类中实现 exec 和 stop方法
- exec 方法是脚本真正执行调用的方法
- stop 方法是脚本被停止的时候调用的方法，这里要做资源的回收


### 运行与调试

- 如果机器已经root过，请在运行的时候对APP进行授权
- 如果非Root机器，请查看请查看[环境构建工具](zh-cn/dev-tools)

?> 运行和调试都按照Android的标准步骤即可，注意需要关闭 Instant Run 功能。[如何关闭 Instant Run](https://blog.csdn.net/yu544324974/article/details/52472641)


### 打包发布

?> 打包发布按照Android的标准步骤即可

### 混淆配置




> ```proguard
> -keep class android.support.**{*;}
> -keep public class * extends android.support.v4.app.Fragment
> -keep public class * extends android.support.**
> -keep public class * extends android.test.**
> -keep class org.opencv.**{*;}
> -keep class com.gibb.auto.model.**{*;}
> ```













