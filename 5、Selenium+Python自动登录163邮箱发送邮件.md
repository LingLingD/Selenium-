**1、Selenium实现自动化，需要定位元素，以下查看163邮箱的登录元素**

****登录（定位到登录框，登录框是一个iframe，如果没有定位到iframe，是无法定位到账号框与密码框）****
![](https://i.imgur.com/2DHmAV8.png)
****定位到邮箱框（name='email'）****

![](https://i.imgur.com/4mt6Z5q.png)

****定位到密码框（name='password'）****
![](https://i.imgur.com/uhjjd42.png)

****定位到登录按钮（id="dologin"）****
![](https://i.imgur.com/TZDw7EU.png)


**2、代码实现**

>```#coding=utf-8```
>
>```import time```
>```from selenium import webdriver```
>
>```broswer = webdriver.Ie()```
>
>```broswer.get("https://mail.163.com/")```  # 输入指定网址
>
>```broswer.switch_to.frame('x-URS-iframe')```  # 登录框是一个iFrame,无法没有定位到该点，则无法找到账号与密码文本框
>
>```broswer.find_element_by_name('email').clear()```  # 清除账号框信息
>
>```broswer.find_element_by_name('email').send_keys('nancywangdl')```  # 定位到账号框
>
>```broswer.find_element_by_name('password').send_keys('密码')```   # 定位到密码框
>
>```login = broswer.find_element_by_css_selector("#dologin")```  # 定位到登录按钮
>
>```login.click()```    # 点击“登录”按钮
>
>```time.sleep(6)```    # 等待6秒
>
>```broswer.find_element_by_id("_mail_component_70_70").click()```   # 点击“写信”按钮
>
>```time.sleep(2)```
>
>```broswer.find_element_by_class_name('nui-editableAddr-ipt').send_keys('1095936979@qq.com')``` # 输入收件人邮箱
>
>```broswer.find_element_by_xpath("//input[@class='nui-ipt-input' and @type='text' and @maxlength='256']").send_keys(u'测试')```
>
>```xpath = broswer.find_element_by_xpath("//div[@class='APP-editor-edtr']/iframe")```
>
>```broswer.switch_to_frame(xpath)```
>
>```broswer.find_element_by_xpath("//body[@class='nui-scroll' and @contenteditable='true']").send_keys(u'这是一个自动化测试邮件')```
>
>```broswer.switch_to_default_content()```
>
>```broswer.find_element_by_xpath("//div[@class='nui-toolbar-item']/div/span[2]").click()```
>
>```time.sleep(3)```
>
>```broswer.quit()```  # 退出浏览器
　　
