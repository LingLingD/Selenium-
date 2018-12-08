**一：登录**

1.指定浏览器，打开网址：https://github.com/login

2.设置等待时间：

```time.sleep(3)```  
or

```driver.implicitly_wait(3)```

3.输入账号、密码，点击“登录”按钮

![](https://i.imgur.com/PAKlD9r.png) 

**二：检查结果**

1.加入检查点，检查登录后的账号是否是之前账号

2.定位到右上角，获取该账号字段值

3.判断获取的值是否与预期结果一致；若一致则通过测试，若不一致则测试不通过


![](https://i.imgur.com/fYQhHV5.png)
 

**三：退出登录**

1.点击“退出”按钮退出登录

2.关闭浏览器

具体代码如下：

>```#coding=utf-8```
>
>```from selenium import webdriver```
>
>```import time```
>
>```driver = webdriver.Ie()```   # 指定浏览器
>
>```time.sleep(3)```
>
>```driver.get("https://github.com/login")```  # 输入网址
>
>```driver.find_element_by_id("login_field").clear()```
>```driver.find_element_by_id("login_field").send_keys("1415084012@qq.com")```  # 输入账号
>```driver.find_element_by_id("password").send_keys("密码")```             # 输入密码
>
>```driver.find_element_by_css_selector("input[value='Sign in']").click()  # 对应抓包数据的：value="Sign in"```
>
>```time.sleep(3)```
>
>```driver.find_element_by_css_selector(".HeaderNavlink.name.mt-1").click()```
>
>```time.sleep(1)```
>
>```t = driver.find_element_by_css_selector(".dropdown-header.header-nav-current-user.css-truncate>.css-truncate-target").text```
>```print(t)```
>
>
>```if t == "LingLingD": ```  # 判断获得的字段值t是否与预期结果一致
>
>```    print("Sucess")```
>
>```else:```
>
>```    print("Fail")```
>
>
>```driver.find_element_by_css_selector(".dropdown-item.dropdown-signout").click()```   # 点击退出登录
>
>```driver.quit()```
　　

参考文档：[https://www.cnblogs.com/yoyoketang/p/6128596.html](https://www.cnblogs.com/yoyoketang/p/6128596.html)

