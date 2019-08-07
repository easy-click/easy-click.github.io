
## execAsync(Runnable runnable)
* @description 异步执行线程，这里会将Runnable放到线程池中进行管理
* @param runnable Runnable对象

> ```java
> thread.execAsync(new Runnable() {
>             @Override
>             public void run() {
>                 while (!isStop()) {
>                     Log.e("TAG", "run...");
>                 }
>             }
>         });
> ```


## execFuncSyncNotNull(ExecFunc<T> condition, long timeout)
* @description 执行某个函数并且等待结果不为空时返回，如果函数中返回的不是空，该方法将立刻执行完毕
* @param condition 条件函数
* @param timeout   超时时间，单位是秒
* @return 返回一个对象


> ```java
>  Object object = thread.execFuncSyncNotNull(new ExecFunc<Object>() {
>             @Override
>             public Object execute() {
>                 if (pkg.equalsIgnoreCase("com.tencent.qq")) {
>                     return new Object();
>                 }
>                 return null;
>             }
>         }, 10);
>         if (utils.isObjectNotNull(object)) {
>             event.toast("检测成功");
>         } else {
>             event.toast("检测失败");
>         }
> ```



## execFuncAndWait(ExecFunc condition, long timeout)
* @description 执行某个函数并且等待true返回，如果函数中返回的是true，该方法将立刻执行完毕
* @param condition 条件函数
* @param timeout   超时时间，单位是秒
* @return 返回一个布尔型对象

> ```java
>  //演示打开微信的监测，超时时间为10秒，如果10秒都为打开，说明打开微信失败了
>        Boolean openMM = thread.execFuncAndWait(new ExecFunc() {
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