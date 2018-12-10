**1.打开网址：[http://tungwaiyip.info/software/HTMLTestRunner.html](http://tungwaiyip.info/software/HTMLTestRunner.html)，下载HTMLTestRunner.py**

**2.copy其HTMLTestRunner.py的内容，在python路径下的lib包下，新建.py后缀名的，粘贴copy内容**
![](https://i.imgur.com/oUigfwJ.png)

**3.若Python版本是2.0，上述操作即可导入HTMLTestRunner，但是python3存在不同，需要改变以下内容**

>（1）在94行，将 import StringIO 改成import io
>
>（2）539行 self.outputBuffer = StringIO.StringIO() 要改成self.outputBuffer = io.BytesIO()
>
>（3）定位到642行，if not rmap.has_key(cls): 需要换成 if not cls in rmap:
>
>（4）772行，把 ue = e.decode('latin-1') 直接改成 ue = e 。
>
>（5）766还有类似的uo = o.decode('latin-1')，改成 uo=o ；
>
>（6）768行的 uo = o ，直接改成 uo = o.decode('utf-8') 。
>
>（7） 774还有类似的  ue = e， 改成 ue = e.decode('utf-8')。
>
>（8）到631行，把print的语句修改掉，原来是print >>sys.stderr, '\nTime Elapsed: %s' % >(self.stopTime-self.startTime)， 可改成 print('\nTime Elapsed: %s' % >>>>(self.stopTime-self.startTime),file=sys.stderr)
>
>（9）定位到118行，把 self.fp.write(s) 修改为 self.fp.write(bytes(s,'UTF-8')) 即可。

**4.做完以上操作即可，成功的标志后如图所示：**

![](https://i.imgur.com/HPY5FTO.png)

 
