**1、打开PyCharm，新建一个python.file，输入代码“from selenium import webdriver”报错的解决方法**

（1）PyCharm没有找到正确的python，在“File  -- Setting --Project Interpreter ”
![](https://i.imgur.com/71IC6k2.png)

（2）操作完上一步后，还需要安装相关插件

![](https://i.imgur.com/ONcg84U.png)

![](https://i.imgur.com/qEOICeY.png)
**2、在python.file，输入代码以下报错的解决方法**

代码：

>```driver = webdriver.Ie()```    //指定IE浏览器
>
>```driver.get("http://www.baidu.com")```  //指定打开的网址
>
>```driver.find_element_by_id("kw").send_keys("Python")```  //kw是百度文本框的id，可以F12查看，在百度输入框输入“Python”
>
>```driver.find_element_by_id("su").submit() ```         //su是按钮“百度一下”的id,可以在
F12查看，点击按钮提交

正确的效果为：

![](https://i.imgur.com/A2O9ots.png)

 

若只弹出IE进入百度页面，且PyCharm报错“Unable to find element on closed window”

可查看该教程：[https://blog.csdn.net/angel_xiaa/article/details/52212340](https://blog.csdn.net/angel_xiaa/article/details/52212340)

