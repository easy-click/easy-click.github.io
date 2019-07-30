
TestCaseStarter类是启动、停止脚本，云控截屏功能的集合,
TestCaseStarter.getInstance(context)直接取得实例.
## generateUiView(final String assetsFile, boolean bindEvent)
* @description 生成UI视图
* @param assetsFile 字符串，assets文件夹中的ui文件名称
* @param bindEvent 布尔型，是否绑定点击事件，如果绑定，将会点击启动按钮时候,自动启动脚本
* @return View 视图对象

        View view = TestCaseStarter.getInstance(context).generateUiView("ui.json",true);


## getUIParamJson(String assetsFile) 
* @description 取得UI界面的参数
* @param assetsFile 字符串，生成界面参数的配置文件名称
* @return JSONObject JSON数据结构的对象

        JSONObject json = TestCaseStarter.getInstance(context).getUIParamJson("ui.json");