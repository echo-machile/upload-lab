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

