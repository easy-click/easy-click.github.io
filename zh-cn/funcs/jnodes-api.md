
* JNodes是用来对节点进行层级筛选，使用了链式选择
    * 示例：
选择ListView下的TextView 并且进行点击

JNodes.root(): 代表产生一个空节点
.select() 代表开始选择
.click() 代表点击

> ```java
> JNodes.root()
>                 .className("android.widget.ListView")
>                 .select()
>                 .className("android.widget.TextView")
>                 .select().click();
> ```


- 更多使用方法请查看javadoc