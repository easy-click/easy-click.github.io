## thread-api



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