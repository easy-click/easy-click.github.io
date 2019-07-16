### 加入类库
- 在Android Studio 项目中 build.gradle 文件中加入私服仓库
> ```gradle
maven {
    url "https://raw.githubusercontent.com/easy-click/easyclick-sdk-repo/master/"
}
> ```

- 加入类库引用
> ```gradle
implementation 'com.android.support:appcompat-v7:28.0.0'
implementation 'com.android.support:design:27.1.1'
implementation group: 'com.android.support', name: 'support-v4', version: '27.1.1'
implementation group: 'com.gibb', name: 'easyclick', version: '1.0.2', ext: 'aar'
> ```


 


### 定义入口类

- 新建 com.run.Main类 并继承 com.gibb.auto.open.TestCaseMain

### 编写主任务

?> 主任务是指包含子任务的入口集合，为了更清晰，逻辑上划分的主、子任务

- 在com.run.Main类中实现 exec 和 stop方法
- exec 方法是脚本真正执行调用的方法
- stop 方法是脚本被停止的时候调用的方法，这里要做资源的回收

### 编写子任务

?> 子任务是单个功能模块
- 新建任意类，继承 com.gibb.testcase.XtsSubTestCase
- 实现构造函数，并传入com.gibb.auto.open.TestCaseApi实例
- 实现 exec 和 stop方法
- exec 方法是脚本真正执行调用的方法
- stop 方法是脚本被停止的时候调用的方法，这里要做资源的回收
- 子任务写完之后，在 com.run.Main#exec方法中进行实例化并调用即可
- 实际子任务可以查看 今日头条的示例 (JRTT.java)


### 运行与调试

?> 运行和调试都按照Anroid的标准步骤即可，注意需要关闭 Instant Run 功能。[如何关闭Instant Run](https://blog.csdn.net/yu544324974/article/details/52472641)


### 打包发布

?> 打包发布按照Anroid的标准步骤即可

### 混淆配置

> ```java

> ```